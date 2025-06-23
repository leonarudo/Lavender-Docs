# ConversationPatcher class
<br>

## Definition
Namespace: Lavender.DialogueLib <br>
Source: [ConversationPatcher.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender/DialogueLib/ConversationPatcher.cs)

## Usage
The base class for any dialogue patching.  

1. Make a child class in your mod and implement the `PatchDialogue()` function.
2. Ensure that your child class's constructor correctly passes the name of the conversation to patch to the base constructor (see below).
3. In your mod's Start, create and register an instance of the child class with `Lavender.AddConversationPatcher()`.  It is safe to keep a reference to the patcher object in your mod.


Once passed to Lavender, you no longer have to manage the object's lifespan, and can assume it will remain valid for the duration of the play session.
The name of the conversation to patch MUST be passed to ConversationPatcher's constructor from your child class's constructor:
```
public class TatyanaConversation : ConversationPatcher
{
  public TatyanaConversation()
    : base("Tenement/Outside/Tatyana Gopnikova")
  {
    
  }
}
```

## Usage Examples
Examples of the ConversationPatcher in action can be see in the Lavender Test project: 
* [TestConversationPatcherTatyana.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender.Test/TestConversationPatcherTatyana.cs)
* [TestConversationPatcherTatyana2.cs](https://github.com/leonarudo/Lavender/blob/main/Lavender.Test/TestConversationPatcherTatyana2.cs)

Note that both of these files patch the same conversation at the same time.  They avoid conflict by not relying on hard node IDs, and instead using Lavender's utility functions to find which nodes to best respond to

<br> 

## Static Properties

<table>
<tr>
  <td>Pause</td>
  <td>A convenience definition to insert a "pause" command into a dialogue line: $"Wait for it.{Pause}.{Pause}.{Pause}.  BOOM!"</td>
</tr>
<tr>
  <td>Quote</td>
  <td>A convenience definition to insert a quotation mark into a dialogue line: $"He said {Quote}She said{Quote}"</td>
</tr>
<tr>
  <td>Lua("Lua script")</td>
  <td>Note: Actually a method, but it belongs with Pause and Quote.  Convenience definition to insert a parsable Lua script into dialogue text: $"You owe me {Lua("GetOwedMoney()")} coins."</td>
</tr>
</table>

<br>

## Properties

<table>
<tr>
  <td>Conversation</td>
  <td>The Conversation object in the PixelCrushers DialogueSystem.<br>Note that this reference is ONLY guaranteed valid while executing PatchDialogue or OnConversationStarted</td>
</tr>
<tr>
  <td>ConversationName</td>
  <td>String name of the conversation this patcher modifies.  Immutable.</td>
</tr>
</table>

<br>

## Virtual Methods (for implementation in child classes)

<table>
<tr>
    <td>PatchDialogue()</td>
    <td>Implement in your child class and perform all logic you need to patch the dialogue.  This is the ONLY time that it is safe to patch dialogue.</td>
</tr>
<tr>
  <td>OnConversationStarted(InteractableTalk)</td>
  <td>Called just before the fullscreen dialogue UI opens.  If you want to register Lua functions that are ONLY available while this conversation is active, then do so within this function</td>
</tr>
  <tr>
    <td>OnConversationEnded(InteractableTalk)</td>
    <td>Called when the fullscreen dialogue UI has closed. If you have conversation-specific Lua functions, make sure to unregister them here
        <br>WARNING! This can be called multiple times (up to 4 times for each OnConversationStarted call).</td>
  </tr>
</table>

<br>

## Methods

<table>
<tr>
    <td>PlayerSays(string)</td>
    <td>Create a new DialogueEntry spoken *by* the player belonging to this conversation.  It still needs to be Link().<br>WARNING! Only valid to call inside of PatchDialogue()</td>
</tr>
  <tr>
    <td>NPCSays(string)</td>
    <td>Create a new DialogueEntry spoken *by* the NPC.  It still needs to be Link().<br>WARNING! Only valid to call inside of PatchDialogue()</td>
  </tr>
  <tr>
    <td>Link(DialogueEntry source, DialogueEntry destination, LinkOrdering? ordering = null, ConditionPriority priority = ConditionPriority.Normal)</td>
    <td>Create a dialogue navigation link from source to destination, allowing dialogue to flow (either automatically by NPC speaking or by player selecting a response).  See LinkOrdering to control where player responses appear in the UI</td>
  </tr>
  <tr>
    <td>GetResponsesTo(DialogueEntry)</td>
    <td>Return an IEnumerable<DialogueEntry> of entries belonging to this conversation that are valid NPC and/or player responses to the provided entry.</td>
  </tr>
  <tr>
    <td>GetStaticResponsesTo(DialogueEntry)</td>
    <td>Return an IEnumerable<DialogueEntry> of entries belonging to this conversation that are valid NPC and/or player responses to the provided entry.  Excludes any responses with Lua criteria, formatting, or callbacks.</td>
  </tr>
  <tr>
    <td>AdvanceToRespondable(DialogueEntry)</td>
    <td>Return an IEnumerable<DialogueEntry> of the soonest entries in the dialogue tree where the player can insert a response choice.  This may be the same entry as passed in, or it may be multiple entries at the same depth.</td>
  </tr>
</table>

<br>
