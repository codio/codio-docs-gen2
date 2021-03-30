.. meta::
   :description: Custom Button

## Custom Buttons
Custom buttons are a powerful feature that let you insert a button into your guide content that when pressed can carry out any custom action.

There are a number of ways to use a custom button

### To jump to a page in the content
This will jump to a specific page in the guide

```javascript
{Button Text | go-to-section-titled}(section title)
```

e.g.
```javascript
{Go to Section: LTI | go-to-section-titled}(LTI)
```

### To launch a process
This will launch a process and execute a terminal command.

```javascript
{Button Text}(command paramater1 parameter2 parameterN)
```

### Launching a process in a terminal window
There are cases where you will want to launch a command in a dedicated terminal window. A typical example is when student code requires input from the user. Codio cannot handle standard input through the guides window, so use the following button command.

```bash
{Button Text | terminal}(command)
```
### Launching a debugger configuration
You can launch a debugger configuration as shown below. It is important to specify the configuration name exactly.

```bash
{Button text | debugger}(debugger configuration name)
```
<a name="restorebutton"></a>
### To restore current files in guides
Students can restore current files to the default setting from the [setting](/students/#guides) menu but you can also offer them a button within your guides content as well.

```bash
{Button text | reset}(optional commands to run)
```

### Writing a custom event handler
This offers you the most flexibility and allows you to write your own custom button press handler. A common use case is executing tests on user code.

To do this, you should use the following format for your custom button.

```bash
{Button Text|custom}(myId)
```
If you wish to use a custom event handler to allow students to restore current files and handle other functions, you can do so but you will need to include this code in your custom script

```bash
window.addEventListener('codio-button-custom', function (ev) {
  if(codio) {
    codio.resetCurrentFiles()
  }
});
```

#### Loading Scripts
You should point your content page to a script file to load javascript scripts. You can do this from **Settings>Global>Scripts**.


![authtoken](/img/guides/scripts.png)

<a name="eventlistener"></a>

#### Event Listener
The event listener is able to execute your custom task. It will display a custom message area beneath it into which you can write your own results data. The message data can be a custom message that a test might return and can be plain text or HTML.

For the event listener to run you should include in **Settings>Global>Scripts**:

- https://codio.com/codio-client.js (where your account is running on codio.com)
- https://codio.co.uk/codio-client.js (where your account is running on codio.co.uk)


The icon that appears in the top left of the message area can be controlled from your event listener, as shown in the example below.

```javascript
window.addEventListener('codio-button-custom', function (ev) {
  console.log('id:', ev.id, 'cmd:', ev.cmd, ev);
  if (codio) {
    codio.setButtonValue(ev.id, codio.BUTTON_STATE.PROGRESS, 'Checking');
	codio.setButtonValue(ev.id, codio.BUTTON_STATE.FAILURE, 'Bad Job :(');
	codio.setButtonValue(ev.id, codio.BUTTON_STATE.INVALID, 'Internal error');
    window.setTimeout(function () {
      codio.setButtonValue(ev.id, codio.BUTTON_STATE.SUCCESS, 'Extremely well done!');
    },1000);

  }
});
console.log('test.js script loaded');
```

- `ev.id` is the contents internal id for the button.
- `ev.cmd` is the `myId` text you specified in the button with `{Button Text|custom}(myId)`. This is typically used to indicate the id of the test you wish to run or just the specific button that is being pressed.

The available button commands are

```javascript
codio.setButtonValue(ev.id, codio.BUTTON_STATE.PROGRESS, 'Checking..');
codio.setButtonValue(ev.id, codio.BUTTON_STATE.SUCCESS, 'Good job!');
codio.setButtonValue(ev.id, codio.BUTTON_STATE.FAILURE, 'Bad Job :(');
codio.setButtonValue(ev.id, codio.BUTTON_STATE.INVALID, 'Internal error');
```

The 3rd parameter can contain any text to display in the button's attached message area. It can be plain text or HTML.
