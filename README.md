1. To start new EmberJS App COMMAND
  ember new <APPNAME>
  //and 'cd' to it.

2. Insert strating HTML, CSS by needs and try to breakdown components into smaller pieces.

3. To generate NEW component COMMAND
  ember generate component <NAME>.
  //If the component can be break into smaller components do that too

4. To keep filesystem clean put component's children to folder with name of component. 

___________________________________________________________________________

EXAMPLE: Component parent name is RECEIVED MESSAGE make folder with same name and MOVE children components into this RECEIVED MESSAGE FOLDER.

app/
  components/
    received-message.hbs
    received-message/
      avatar.hbs
      username.hbs

To REFERENCE this NESTED files we need to use SYNTAX of ::
//     folder   :: file
<ReceivedMessage::Avatar>
//     folder   ::  file
<ReceivedMessage::Username>

---------------------------------------------------------------------------

5. received-message/avatar and sent-message/avatar files are almost the same. Only thing they have different it's content. To make it more REUSABLE way:
  1. Make avatar.hbs in the components FOLDER with 
    <aside ...attributes>
      <div class="avatar" title={{@title}}>{{@initial}}</div>
    </aside>
  2. Call that component with <Avatar> tag in the file we want to use it
  3. Assign <Avatar @title="Some title" @initial="T">
We will make this attribues and content of DIV dynamic by {{@initial}}