# DHTML Style Guide Working Group

The DHTML Style Guide Working Group (DSGWG) has come together to create a recommendation for keyboard shortcuts to be used in website widgets. We realize that many keystrokes are already in use by various operating systems, user interfaces, and assistive technology. Therefore our task is to recommend the best, most intuitive, most international friendly shortcut keys possible without regard to their current use. It is hoped that developers, AT vendors, and Browser manufactures will use these as guidelines, but understand it may not be practical or possible given their individual constraints.

* * *

## Table of Contents

*   [Widgets](#widgets)
    1.  [Accordion](#accordion) see [Tab Panel](#tabpanel)
    2.  [Alert](#alert)
    3.  [Auto Complete](#autocomplete)
    4.  [Button](#button)
    5.  [Check Box](#checkbox)
    6.  [Combo Box](#combobox)
    7.  [Date Picker](#datepicker)
    8.  [Dialog (Modal)](#dialogmodal)
    9.  [Dialog (Non-Modal)](#dialognonmodal)
    10.  [Dialog (Tooltip)](#dialogtooltip)
    11.  [Drag & Drop](#draganddrop)
    12.  [Grid/Tree Grid](#grid)
    13.  [Landmark Navigation](#landmarks)
    14.  [Link](#link)
    15.  [Listbox](#listbox)
    16.  [Media Player](#mediaplayer)
    17.  [Menu](#menu)
    18.  [Menu Button](#menubutton)
    19.  [Popup Menu](#popupmenu)
    20.  [Popup Help (aka Bubble Help)](#popuphelp)
    21.  [Radio Button](#radiobutton)
    22.  [Rich Text Editor](#richtext)
    23.  [Slider](#slider)
    24.  [Slider (Multi-Thumb)](#slidertwothumb)
    25.  [Spinbutton](#spinbutton)
    26.  [Tab Panel](#tabpanel)
    27.  [Tool Bar](#toolbar)
    28.  [Tooltip Widget](#tooltip)
    29.  [Tree View](#treeview)
    30.  [Window Splitter](#windowsplitter)
    31.  [Wizard](#wizard)
*   [Global Recommendations](#global)
*   [ARIA Gap Analysis](#gap)
*   [Participants and Contributors](#participants)

For more information about Key-navigable custom JavaScript widgets see the [Codetalks Wiki](https://web.archive.org/web/20130127004544/http://wiki.codetalks.org/wiki/index.php/Docs/Keyboard_navigable_JS_widgets).

* * *

## <a name="widgets">Widgets</a>

1.  ## <a name="accordion">Accordion</a>

See [Tab Panel](#tabpanel).

* * *

4.  ## <a name="alert">Alert</a>

Example: A message with important information ([ARIA Alert](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#alert)).

Example: [http://devserv.rehab.uiuc.edu/ita/jongund/citaweb/test/aria/alert/alert1.php](https://web.archive.org/web/20130127004544/http://devserv.rehab.uiuc.edu/ita/jongund/citaweb/test/aria/alert/alert1.php)

An alert (ARIA active region) does not require any keyboard support. See [Dialog (Modal)](#dialogmodal), [Dialog (Non-Modal)](#dialognonmodal) and [Dialog (Tooltip)](#dialogtooltip) below.

* * *

9.  ## <a name="autocomplete">Auto Complete</a>

Example: The search tool of a web document ([ARIA Search](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#search)).

A combo-box where the choices offered are filtered by the information typed into the box. An editable auto-complete allows choices that are not in the list to be entered. An example of an editable auto-complete is the URL field in the browsers. An auto complete component consists of a textbox and an associated drop-down list of choices. There is usually an icon associated with the textbox to trigger the display of the drop-down list of choices via the mouse.

Here are the mouse and keyboard gestures to interact with the auto complete component:

*   **Click** on an icon associated with the textbox to display the entire list of choices in a drop-down. Most auto-complete widgets will have an arrow or icon associated with the textbox. If there is no icon, clicking in the textbox will trigger the display of the drop-down.
*   With focus in an empty textbox, press **Arrow Down, Arrow Up, Alt Arrow Down or Alt Arrow Up** to display the entire list of choices - focus remains in the textbox and no choice is highlighted. Press the down arrow to highlight the first choice in the list. Press the up and down arrow keys to highlight the desired choice in the list. Note that the arrows will wrap through the textbox when the top or bottom of the list is reached. For example, pressing the down arrow when the last choice is highlighted will move focus back to the textbox, pressing down again will move focus to the first item in the list. Likewise, with focus in the textbox and the list displayed, pressing up arrow will move focus to the last item in the list. When a choice is highlighted using the arrow keys, the highlighted choice is displayed in the textbox. Press enter or click on the highlighted choice to select it and close the drop-down list. This mimics the behavior of the HTML select element.
*   With the drop-down list of choices displayed, move the mouse pointer over an item in the list to highlight it. The textbox value is not modified when the mouse is used to highlight a choice. Clicking on the highlighted choice will close the drop-down and update the textbox with the selected choice. This mimics the behavior of the HTML select element.
*   With focus in an empty textbox, type **Any Letter** If any of the available choices begin with the letter typed, those choices are displayed in a drop down. Keyboard and mouse behavior in the drop-down matches that described above. If the letter typed does not match any of the available choices the drop-down list is not displayed.
*   With focus in textbox with an existing value type **Additional Letters.** As the user types letters the list of choices is filtered so that only those that begin with the typed letters are displayed. Until the user presses the arrow keys to highlight a particular choice, only the typed letters are displayed in the textbox. In an editable auto-complete, If there are no choices that match the letter(s) typed, the drop down list of choices is closed. In a non-editable auto-complete any letters which do not result in a match from the list are ignored, the drop down list of choices remains static until the user presses escape to clear the text field, backspaces to remove some of the letters previously typed, or types an additional letter that results in a valid list of choices. Navigation through the list of choices and display of the highlighted choice in the textbox works as described above.  
    _Optional: When a choice is highlighted via arrow key navigation, the input cursor is left at the end of the typed entry and the highlighted choice is displayed in the textbox with the characters after the input cursor selected. Typing an additional character will remove the auto-completed portion and append the newly typed character to the end of the previously typed characters. The list will be filtered based on the additional character(s) typed._
*   With focus in a textbox, type **Escape**
    *   If there is no text in the textbox, pressing escape closes the drop-down if it is displayed.
    *   For an editable autocomplete that has text in the textbox that was both typed by the user and auto-completed by highlighting a choice using the keyboard, the auto-completed portion of the text is cleared and the user typed characters remain in the textbox. The drop-down list is closed. To completely clear the textbox contents the user must use the backspace key to remove the typed characters. This is how the Google search box in the Firefox UI works. _Recommend that (unlike the Google example), pressing the escape key again completely clears the textbox rather than relying on only the backspace key._
    *   For a non editable auto-complete that has text in the textbox that was both typed by the user and auto-completed by highlighting a choice using the keyboard, pressing escape closes the drop-down list and leaves the current choice in the textbox.
    *   For an editable or non-editable auto complete with text in the textbox that was typed by the user and the mouse is highlighting a choice in the drop down (keyboard navigation was NOT used), pressing escape closes the drop down and leaves the typed text displayed in the text box. Need to consider if pressing escape again should clear the typed text. The user must press the down arrow or alt down arrow or click the associated icon to invoke the drop-down list of choices again.
*   Moving focus out of an empty auto complete field where a value is required should either invoke an error or if a default value was initially assigned, reset the value to the default value.
*   Moving focus out of an auto complete field that does not contain a valid entry should either invoke an error or if a default value was initially assigned, reset the value to the default value.
*   **Note:** It is good practice to limit the number of matching items in the drop down to a reasonable number. The reasonable number is determined by the task at hand. A list of the 50 US States is probably reasonable but a list containing all of the office numbers in a building is probably not appropriate.

* * *

15.  ## <a name="button">Button</a>

Example: Allows for user-triggered actions ([ARIA Button](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#button)).

*   **Spacebar or Enter keys** executes the action for that button.
    *   If the button activation closes the containing entity or launches another entity, then focus moves to the newly opened entity.
    *   If the button activation does not close or dismiss the containing entity, then focus remains on the button. An example might be an Apply or Recalculate button.

* * *

19.  ## <a name="checkbox">Checkbox</a>

Example: A control that has three possible values: "true", "false", or "mixed" ([ARIA Checkbox](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#checkbox)).

*   Two State Check Box
    *   **Space Bar** key toggles the selection, checking or unchecking the box.
*   Three State Check Box
    *   If not checked, **space** checks the check box
    *   If checked, **space** unchecks the check box
    *   If partially checked, **space** unchecks the check box.

* * *

23.  ## <a name="combobox">Combobox</a>

Example: Combobox is the combined presentation of a single line textbox with a drop down select widget. The combobox may be editable. Typically editable combo boxes are used for autocomplete behavior, and the autocomplete property would be used on the child textbox. ([ARIA Combobox](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#combobox))

*   **Tab** moves focus into the edit field (Edit field to hold value of selected item in the dropdown list). A second Tab key selects the current item on the list, updates the edit field, closes the dropdown list, and moves focus to the next focusable item in the tab order.
*   **Alt Down Arrow and or Space** opens the dropdown list and moves focus to the selected option. (If nothing is selected, then focus moves to the first option in the list). If the combobox is not editable, then the space bar may also be used to open the dropdown list.
*   **Up and Down Arrow** moves focus up and down the list. As focus moves inside the dropdown list, the edit field is updated.
*   **Enter** selects the current item on the list, updates the edit field, highlights the selected item in the dropdown list, closes the dropdown list and returns focus to the input field.
*   **Escape key** closes the dropdown list, returns focus to the edit field, and does not change the current selection.
*   **Typing a letter (printable character) key** moves focus to the next instance of a visible node whose title begins with that printable letter.

* * *

27.  ## <a name="datepicker">Date Picker</a>

( [Complete proposal from Chris Blouch](https://web.archive.org/web/20130127004544/http://dev.aol.com/downloads/DatePicker.txt))

Example: Choose a date from a month view of a calendar. Day and hour views are not a part of this discussion.

*   **TAB** Like other widgets the date picker widget receives focus to become active by tabbing into it. Once focused is received focus is repositioned on todays date in a grid of days and weeks. A second tab will take the user out of the date picker widget. Focus initial is placed on todays date.
*   **Shift Tab** reverses the direction of the tab order. Once in the widget, a Shift Tab will take the user to the previous focusable element in the tab order.
*   **Arrow Up and Down** goes to the same day of the week in the previous or next week respectively. If the user advances past the end of the month they continue into the next or previous month as appropriate.
*   **Arrow Left and Right** advances one day to the next, also in a continuum. Visually focus is moved from day to day and wraps from row to row in a grid of days and weeks.
*   **Control Page Up** Moves to the same date in the previous year
*   **Control Page Down** Moves to the same date in the next year
*   **Space**
    *   Singleton Mode: acts as a toggle either selecting or deselecting the date.
    *   Contiguous Mode: Similar to selecting a range of text. Space selects the first date. Shift Arrows add to the selection. Pressing Space again deselects the previous selections and selects the current focused date.
    *   Non-Contiguous Mode: Space may be used to select multiple non-contiguous dates.
*   **Home** Moves to the first day of the current month.
*   **End** Moves to the last day of the current month.
*   **Page Up** Moves to the same date in the previous month
*   **Page Down** Moves to the same date in the next month
*   **Enter Key** Submits the form
*   **Escape** in the case of a popup date picker, closes the widget without any action.
*   **Note:** Navigation into the past is optional

* * *

32.  ## <a name="dialogmodal">Dialog (Modal)</a>

Example: A dialog is a small application window that sits above the application and is designed to interrupt the current processing of an application in order to prompt the user to enter information or require a response ([ARIA Dialog](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#dialog)).

A modal dialog is a dialog that takes and holds focus until the dialog is closed or submitted.

*   **ENTER** If the purpose of the dialog is to gather information, the dialog should have a mechanism to submit the data gathered usually via a keyboard accessible button. The Enter key should serve as the default submit action.
*   **ESC** There should be a method to close the dialog without taking any action. This could be implemented via a cancel button which is keyboard accessible. It is recommended that a dialog also be cancelled by pressing the escape key with focus on any item.
*   **Tab** Focus must be held within the dialog until it is cancelled or submitted. As the user presses tab to move within items in the dialog, pressing tab with focus on the last focusable item in the dialog will move focus back to the first focusable item in the dialog.
*   **Shift Tab** Likewise, if the user is shift-tabbing through elements in the dialog, pressing shift-tab with focus on the first focusable item in the dialog will move focus to the last item in the dialog.
*   **Note:** If the current focus item has escape key behavior, the press of the escape will be handled by the current item and the user may have to press escape an additional time to close the dialog.
*   **Note:** Even if the user clicks outside of the dialog on the application which invoked the dialog, focus remains in the dialog.
*   **Note:** Because the dialog is modal and the user can not interact with the invoking application while the dialog is displayed, there is not a requirement to make the dialog moveable via the mouse although this behavior is recommended.
*   **Note:** When the dialog is closed or cancelled focus should return to the element in the application which had focus before the dialog is invoked. This is usually the control which opened the dialog.
*   **Note:** When a modal dialog opens focus goes to the first focusable item in the dialog. Determining the first focusable item must take into account elements which receive focus by default (form fields and links) as well as items which may have a tabindex attribute with a positive value. If there is no focusable item in the dialog, focus is placed on the dialog container element.

* * *

37.  ## <a name="dialognonmodal">Dialog (Non-Modal)</a>

Example: A dialog is a small application window that sits above the application and is designed to interrupt the current processing of an application in order to prompt the user to enter information or require a response ([ARIA Dialog](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#dialog)).

A non-modal dialog is one which is displayed and focusable at the same time as the application which invoked it. Also like the modal dialog, focus via the tab and shift-tab key must be maintained within the dialog. However, a non-modal dialog should have a keyboard mechanism to return focus to the application while leaving the dialog open.

*   **ESC** cancel the dialog without taking any action
*   **ENTER** method to submit any data gathered in the dialog.
*   **F6** The F6 key is the recommended key to move focus between the application and an open non-model dialog.
*   **Note:** The mouse user may click on either the application or the dialog to change focus between the two.
*   **Note:** In a Web application the non-modal dialog is usually always displayed above the application page, rather than in a separate browser window but that is not a requirement.
*   **Note:** This dialog box is dragable by the mouse user and an equivalent behavior ([Drag & Drop](#draganddrop)) should be offered to the keyboard only user.

* * *

43.  ## <a name="dialogtooltip">Dialog (Tooltip)</a>

Example: A popup that displays a description for an element when a user passes over or rests on that element. Supplement to the normal tooltip processing of the user agent. ([ARIA Tooltip](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#tooltip)).

A tooltip dialog is a modal dialog that is rendered near the invoking element and visually connected via a cartoon bubble-like protrusion.

*   **ESC** The tooltip dialog is closed by pressing the escape key when focus is within the dialog, mouse clicking on a close icon, or mouse clicking outside of the dialog onto the application.
*   **Tab** Focus must be held within the dialog until it is cancelled or submitted. As the user presses tab to move within items in the dialog, pressing tab with focus on the last focusable item in the dialog will move focus back to the first focusable item in the dialog.
*   **Shift Tab** Likewise, if the user is shift-tabbing through elements in the dialog, pressing shift-tab with focus on the first focusable item in the dialog will move focus to the last item in the dialog.
*   **Note:** It is modal because focus is trapped within the dialog as the user navigates via the tab and shift-tab key.
*   **Note:** Unlike a true modal dialog, the user can click outside of the dialog, however in that case the tooltip dialog is immediately closed.
*   **Note:** A tooltip dialog can not be moved/dragged.
*   **Note:** Other than the close and move behavior, all other behaviors of a modal dialog are implemented by the tooltip dialog.

* * *

48.  ## <a name="draganddrop">Drag and Drop</a>

See ARIA [Drag & Drop](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria-practices/#dragdrop)

A drag and drop operation is available in contexts where the widget supports selection of objects, including single and multiple selection models. An example is a [Treeview](#treeview). The widget is a container of one or more objects that are potentially draggable.

Draggable objects are identified using the property "aria-grabbed". If the aria-grabbed property is absent, or if it has the value "undefined", then the object cannot partake in drag and drop.

Other objects are potential drop targets. Drop targets are identified using the property "aria-dropeffect" set to one or more of its values.

*   **Space** When focused on an object that is draggable but not selected (aria-grabbed=false), the Space key marks the object and adds it to the set of objects to be dragged, clearing any previously marked objects. The object's aria-grabbed state is set to "true". The Space key is used to mark a single object, or to mark a range of objects by using it in conjunction with Shift or Control.
*   **Shift Space** When focused on an object which supports drag and drop, the Shift Space creates an inclusive contiguous set selecting all objects between the current one and the previously marked object. A second Shift Space modifies the extent of the contiguous set by deselecting everything and creating an inclusive contiguous set selecting objects between the new current object and the previously selected object.
*   **Control Space** When focused on an object that is draggable, Control Space toggles the object's membership in the set of draggable objects. In this way, Control Space can be used to create a discontiguous set of draggable objects. The aria-grabbed property of the objects is toggled between "true" and "false".
*   **Control M*** Indicates all the objects have been selected, and are ready to be dragged. Because calculating the set of available drop points based on the type of objects in the selected set is computationally expensive, the user needs to signal that their selection process is complete by pressing Control-M.
*   **Navigate** to the drop target using standard navigation keys available in the particular widget. (Tab, Arrow, etc).
*   **Shift F10** Optionally invokes a list of possible drop targets. The user can navigate the list to choose a drop target to complete the operation.
*   **Control M*** When focus is on a drop target (aria-dropeffect is set on the focused object), at the developer's option, provides the most intuitive type of drop, either copy, move, execute, or a shortcut.
*   **Shift Control M*** When focused on an object that is a drop target (aria-dropeffect set), Shift Control M presents a menu that will allow one or more of copy, move, execute, create a shortcut, or cancel. The values in the menu corresponds one-to-one with the values of the aria-dropeffect property.
*   **Escape**
    *   If interacting with the list invoked using Shift F10, or the menu invoked using Shift Control M (see above), Escape dismisses the list or menu. Focus is set to the object from which the user invoked the list or menu.
    *   In all other cases, abandons the drag and drop operation and deselects all objects.
*   *** Note:** While there is value to grabbing and dropping being invoked by the same key (Control M), some may find using the keystrokes associated with cut and paste will incur a lower cognitive load. Granted that many drag and drop operations do not map well to the mental model of cutting and pasting, the behaviors and commands are sometimes close enough as to be easier to understand than a new generic command. Using the X and V key combinations is therefore a choice to be made by the widget implementor. Likewise, some would argue that a different letter such as G for grab would make more sense. Be aware that Control-G is already used on some browsers but other combinations such as Alt-G are usually available. Also there are diminishing returns with internationalization breaking many English letter to word mappings, so choosing G (or any other letter) over M may not improve cognitive load in non-English implementations.
*   **Note:** It is recommended that other methods of performing the same operation without drag and drop may be the best way to meet the accessibility requirements. As an example, when moving a mail message from the inbox to another folder, a list of those folders could be presented in a select list as an alternative.
*   **Note:** Selection of the objects to be moved may differ depending on the type of object or objects to be dragged and what type of widget in which they are contained. Example. A list of emails that might be selected one at a time or many at a time in contiguous or non-contiguous manner using the Space and Shift Space keys as indicated above. However, text in a document might better be selected by positioning the cursor at the beginning of a word and holding down the shift key while using the Arrow keys Left and Right to mark the letters you wish to move.
*   **Note:** Dropping is only allowed on one drop target at a time. The user may have to drag and drop several times to accomplish multiple tasks.

* * *

55.  ## <a name="grid">Grid/Tree Grid</a>

Example: A grid (e.g. a data table) of ARIA role Grid. ([ARIA Grid](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#grid))  
Example: A data table containing rows and cells of read only information  
Example: A webmail inbox containing checkboxes, links, and read only information arranged in rows and columns.  
Example: A teacher's online gradebook containing select lists, text input fields and read-only information arranged in rows and columns.

*   **Tab**
    *   The initial tab enters the grid with focus on the first cell of the first row, often a header.
    *   A second tab moves out of the grid to the next tab stop on the page.
    *   Once focus is established in the grid, a TAB into or a Shift Tab into the grid will return to the cell which last had focus.
*   **Left and Right Arrow** Move focus to the adjacent column's cell. There is no wrap at the end or beginning of columns.
*   **Up and Down Arrow** Move focus to the adjacent row's cell. There is no wrap at the first or last row.
*   **Home** moves focus to the first cell of the current row
*   **End** moves focus to the last cell of the current row
*   **Page Up** moves focus to the first cell in the current column
*   **Page Down** moves focus to the last cell in the current column
*   **Enter or F2** pressed while focus is on a cell containing an actionable item will enter Actionable Mode. Pressing the **Tab** key while in actionable mode moves focus to the next actionable item within the grid, wrapping when the last actionable item in the grid is reached. **Shift Tab** does the same as Tab but in reverse order.

    **Option** the author may choose to enable 'auto action' on a cell in order to avoid having to press enter or F2 a second time to activate the default behavior of the object contained in a cell. For example, if the cell contains a single link the author may want to have enter follow the link rather than just move focus to it. This auto action mode should be configurable on a per cell basis as its utility is dependent on each cell's content. For example, if the cell contains multiple links, auto action should be disabled as its behavior would be ambiguous.

    **Option** the author may choose to implement Enter or F2 as a toggle such that pressing these keys multiple times will enter and exit actionable mode. The working group was divided on this point. Some thought this would be confusing while others found it intuitive.

*   **Esc** exits Actionable Mode
*   **Selection** Table selection is a 3x2 matrix of options. We have rows, cells and columns which we want to select either individually or contiguously.

    <table border="1">

    <tbody>

    <tr>

    <th>Object</th>

    <th>Individual</th>

    <th>Contiguous</th>

    </tr>

    <tr>

    <td>Rows</td>

    <td>**shift space**</td>

    <td>**shift arrows** from current position (up/right and down/left functional equivalent)</td>

    </tr>

    <tr>

    <td>Cells</td>

    <td>**space**</td>

    <td>**shift arrows** from current position</td>

    </tr>

    <tr>

    <td>Columns</td>

    <td>**control space**</td>

    <td>**shift arrows** from current position (up/right and down/left functional equivalent)</td>

    </tr>

    <tr>

    <td>Grid</td>

    <td colspan="2">**control A** to select the entire grid.</td>

    </tr>

    </tbody>

    </table>

    **Shift F8** adds additional discontinuous items to the selection set. If the user has already selected a column then shift f8 will add additional columns to the set. Similar behavior for rows and cells.

    See [Global Recommendations](#global) for information on cut, copy and paste.

    **Assumption:** row selection is the most common use case so it is assigned the single key space command.

    **Assumption:** no mixed selections. Selections are either individual or contiguous items and not both at the same time. Selection mode change resets the selections. For example, performing contiguous row selections and then starting selection of individual cells would cause the previously selected contiguous rows to become deselected and a new selection set is started.

    **Option:** the author may choose to disable multiple selections. In this case contiguous is disabled by definition and a second selection will deselect any previous selections. The author may also choose to disable row or column selections as part of disabling multiple selections because in some scenarios these could be functional equivalents of multi-selection.

    **Note:**The author should use different styling for the selection and persist that styling even when the grid does not have focus

### <a name="treegrid">Tree Grid</a>

Example: A grid whose rows can be expanded and collapsed in the same manner as for a tree ([ARIA Treegrid](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#treegrid)).

Example: A Tree Grid is a combination of a Treeview and a Grid with rows that are expandable. Examples include a threaded view of an e-mail grid or a calendar that opens month, week and day views.

![](https://web.archive.org/web/20130127004544im_/http://dev.aol.com/images/TableWithGroupedRows.jpg)

Keyboard controls are the same as a grid with the following additions

*   **Control and Left Right Arrows** Expand or collapse rows.
*   **Up and Down Arrows** The down arrow moves focus to the first column of a child row, if expanded. Otherwise focus is moved to the same column in the next row. Up arrow performs the same navigation but in reverse.
*   **Note:**The author may choose to indent child nodes visually. This should be done with an appropriate number of spacer cells marked as presentation in order to keep the headers aligned.
*   **Note:**If cells are used for padding or layout of the hierarchy, navigation to those presentational cells should be prevented.

* * *

65.  ## <a name="landmarks">Landmark Navigation</a>

Example: ARIA provides for many roles that describe various types of content like Article, Heading, etc. It would be useful to provide a keyboard shortcut that would cycle through these landmarks similar to the way a tab key currently traverses tabstops. ([ARIA: Steps for defining a logical navigational structure](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria-practices/#kbd_layout))

ARIA Landmark Roles:

*   Article
*   Banner
*   Complementary
*   Contentinfo
*   Main
*   Navigation
*   Search

Other ARIA Roles that might benefit from Landmark Navigation:

*   Directory
*   Group
*   Log
*   Status
*   Heading
*   Menu

Keyboard Shortcuts

*   **Control Alt Tab Rotates forward through the landmarks.**
*   **Shift Control Alt Tab reverses the rotation.**
*   **Note:** The group felt that implementation of this would best be left to the browser and not the web page developer.

* * *

76.  ## <a name="link">Link</a>

Example: Interactive reference to a resource (note, that in [XHTML] 2.0 any element can have an href attribute and thus be a link) ([ARIA](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#link) Link).

*   **Tab** moves focus to the Link. A second tab moves focus to the next focusable item.
*   **Space or Enter** executes the link.
*   **Shift F10** is used to bring up an associated [Popup Menu](#popupmenu).

* * *

80.  ## <a name="listbox">Listbox</a>

Example: A widget that allows the user to select one or more items from a list of choices. ([ARIA Listbox](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#listbox)).

*   **Tab:** When a list is tabbed to, select the first item if nothing else is already selected. A second tab will take the user out of the widget to the next tab stop on the page.
*   **Up/down arrow** navigate up and down the list.
*   **Shift up and shift down** move and extend the selection.
*   **Typing letter or several letters** to navigate (same letter goes to each item starting with that, different letters go to first item starting with that entire string).
*   **Shift F10:** If the current item has an associated context menu, then this key combination will launch that menu.
*   **Selection**
    *   Checkbox - **Space bar** toggles [checkboxes](#checkbox), if the list items are checkable
    *   Selectable List Items
        *   **Space** acts as a toggle to select and deselect the current item. If previous items have been selected, it also deselects them and selects the current item.
        *   **Shift Space** selects contiguous items from the last selected item to the current item.
        *   **Control Arrow** moves without selecting.
        *   **Control Space** selects non-contiguous items and adds the current selected item to all previously selected items.
        *   **Control A** It is recommended a checkbox, link or other method be used to select all. The Control A key could be used to provide the shortcut key.
*   **Note:** It is recommended the developer use different styling for the selection when the list is not focused (hint: non-active selection is often shown with a lighter background color).

* * *

84.  ## <a name="mediaplayer">Media Player</a>

Example: A radio or video player.

*   **Control Alt P** = Pause/Play toggle
*   **Control Alt S** = Stop the player (May not be needed if Alt P performs the same functionality.)
*   **Control Alt M** = Mute
*   **Control Alt U** = Volume Up
*   **Control Alt D** = Volume Down
*   **Control Alt 1 â€“ 5** = Change the volume. 1 being the lowest volume and 5 being the loudest.
*   **Control Alt C** Captions toggle.

* * *

88.  ## <a name="menu">Menu</a>

Example: Offers a list of choices to the user ([ARIA Menu](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#menu)).

*   If a menu bar item has focus and the menu is not open, then:
    *   **Enter, Spacebar, and the up down arrow keys** opens the menu and places focus on the first menu item in the opened menu or child menu bar.
    *   **Left or right arrow keys** moves focus to the adjacent menu bar item.
*   When a menu is open and focus is on a menu item in that open menu, then
    *   **Enter or Spacebar** invokes that menu action (which may be to open a submenu).
    *   **Up or down arrow keys** cycles focus through the items in that menu.
    *   **Escape** closes the open menu or submenu and returns focus to the parent menu item.
    *   If the menu item with focus has a submenu, pressing **Enter, Spacebar, or the right arrow key** opens the submenu and puts focus on the first submenu item.
*   When a submenu is open and focus is on a menu item in that submenu:
    *   **Up or down arrow keys** cycle through the submenu items (behaves the same as open menu).
    *   **Escape or the left arrow key** closes the submenu and returns focus to the parent menu item.
*   **Typing a letter (printable character) key** moves focus to the next instance of a visible node whose title begins with that printable letter.
*   First item in menu bar should be in the tab order (tabindex=0).
*   Disabled menu items receive focus but have no action when **enter or left/right arrow** is pressed. It is important that the state of the menu item be clearly communicated to the user.
*   **Tabbing** out of the menu component closes any open menus.
*   With focus on a menu item and a sub menu opened via mouse behavior, pressing **down arrow** moves focus to the first item in the sub menu.
*   With focus on a menu item and a sub menu opened via mouse behavior, pressing **up arrow** moves focus to the last item in the sub menu.
*   With focus on a submenu item, the user must use **arrows or the Escape key** to progressively close submenus and move up to the parent menu item(s).
*   At the top level, **Escape key** closes any sub menus and keeps focus at the top level menu.

* * *

92.  ## <a name="menubutton">Menu Button</a>

    *   **Space or Enter** - With focus on the button pressing space or enter will toggle the display of the drop-down menu. Focus remains on the button.
    *   **Down Arrow**
        *   With focus on the button and no drop down menu displayed, pressing **down arrow** will open the drop-down menu and move focus into the menu and onto the first menu item.
        *   With focus on the button and the drop-down menu open, pressing **down arrow** will move focus into the menu onto the first menu item.
    *   **Up and down arrow** - With focus on the drop-down menu, the **up and down arrow keys** move focus within the menu items, "wrapping" at the top and bottom.
    *   **Escape** - With focus on the drop-down menu, pressing **escape** closes the menu and returns focus to the button.
    *   **Tab Key**
        *   With focus on the button pressing the **tab key** will take the user to the next tab focusable item on the page.
        *   With focus on the drop-down menu, pressing the **tab** key will take the user to the next tab focusable item on the page. Note that this may be difficult to achieve on a web page.
    *   **Typing a letter (printable character) key** moves focus to the next instance of a visible node whose title begins with that printable letter.

* * *

94.  ## <a name="popupmenu">Popup Menu</a>

([Complete proposal from Earl Johnson](https://web.archive.org/web/20130127004544/http://dev.aol.com/downloads/kbd-nav--popup-tool-bubble-022808.html))

Example: The keyboard navigation for this widget was designed to work for both the popup and menubar menu widgets. The goal was to present a desktop paradigm for posting and dismissing menu widgets.

*   **Shift F10**
    *   Posts the Popup Menu Widget When it is used as a [Contextual Menu](https://web.archive.org/web/20130127004544/http://en.wikipedia.org/wiki/Context_menu).
    *   Place input focus on the first available menuitem in the Popup Menu.
    *   **Note:** The Browser's Contextual Menu pops up if the element with input focus does not have a Popup Menu attached.
    *   **Note:** Experiment indicated that Javascript is able to re-purpose to post the widget's popup menu instead of the browser's.
    *   **Note:** Shift F10 is used by IE to "Display a shortcut menu for a link". In IE7 and IE8 event.cancelBubble=true; and event.returnValue=false; will allow the re-purposing of keys used by the browser. In the case of IE6, you can not stop the bubble up of keys used by the browser, but can stop the bubble up to the OS. In the case of Firefox and other standard compliant browsers, event.stopPropagation(); and event.preventDefault(); will re-purpose the keys.
*   **ESC**
    *   Causes no menu action and dismisses Popup Menu
    *   Input focus is returned to the element from which the Popup Menu was called.
*   **Up/Down Arrow**
    *   Moves input focus vertically between each menuitem
    *   Input focus wraps from the last to the first menuitem on a Down key press and vice-versa when the Up key is pressed.
*   **Right/Left Arrow**
    *   Where applicable, causes a sub-menu to post or un-post
    *   Causes no action if there is no sub-menu
*   **Enter**
    *   What occurs when Enter is pressed depends on the state the menu is in:
        *   Posts the Popup Menu if input focus is on the element, or widget it is attached to, e.g., a menubutton, link, etc.:
            *   Input focus is placed on the first menuitem when the menu pops up.
        *   Dismisses the menu when input focus is on an active menuitem.
        *   Nothing occurs if input focus is on a menuitem marked as disabled.
*   **End/Home**
    *   Moves input focus to the last or first menuitem
*   **Page Down**
    *   Moves input focus to the first menuitem on the next view of the menu.
    *   Moves input focus to the last menuitem on menus that display all their content in one view.
*   **Page Up**
    *   Moves input focus to the last menuitem on the previous view of the menu.
    *   Moves input focus to the first menuitem on menus that display all their content in one view.
*   **Tab**
    *   One of the following occurs:
        *   Moves input focus between elements in the Popup Menu's tabbing order.
            *   Input focus stays in the Popup Menu until one of the following occurs:
                *   ESC is pressed.
                *   Enter is pressed when input focus is on an interactive widget/element.
*   **Typing a letter (printable character) key** moves focus to the next instance of a visible node whose title begins with that printable letter.

* * *

99.  ## <a name="popuphelp">Popup Help (aka Bubble Help)</a>

([Complete proposal from Earl Johnson](https://web.archive.org/web/20130127004544/http://dev.aol.com/downloads/kbd-nav--popup-tool-bubble-022808.html))

Popup Help contains more descriptive, or actionable, help-like text and elements. It may contain, and was designed to handle, interactive elements such as a button, link, or text field. It is essentially a Popup Menu with un-necessary keystrokes turned off. The key sequence for posting Popup Help was to take advantage of F1's tie to the Help paradigm (F1 calls up application Help for example).

*   **Control F1**
    *   Posts the Popup Help widget.
    *   Input focus is placed on the first interactive element in the Popup Help.
    *   **Note:** Control F1 is used by IE to "Display a help dialog box". In IE7 and IE8 event.cancelBubble=true; and event.returnValue=false; will allow the re-purposing of keys used by the browser. In the case of IE6, you can not stop the bubble up of keys used by the browser, but can stop the bubble up to the OS. In the case of Firefox and other standard compliant browsers, event.stopPropagation(); and event.preventDefault(); will re-purpose the keys.
    *   **Note:** With the exception of Control F1 to bring up Popup Help this widget is very similar to [Dialog (Modal)](#dialogmodal) and or [Dialog (Non-Modal)](#dialognonmodal) and or [Dialog (tooltip)](#dialogtooltip) described above.
*   **ESC**
    *   Causes no menu action and dismisses Popup Help
    *   Input focus is returned to the element, or widget the Popup Help was called by
    *   Pressing Enter when input focus is on the "X" glyph acts the same as pressing ESC.
*   **Tab**
    *   One of the following occurs:
        *   Modal behavior
            *   Moves input focus between elements in the Popup Help's tabbing order.
                *   Input focus stays in the Popup Help until one of the following occurs:
                    *   ESC is pressed.
                    *   Enter is pressed when input focus is on an interactive widget/element.
        *   Non-Modal behavior
            *   Moves input focus to the next tab able element in the tabbing order if the following applies:
                *   Popup Help is posted.
                *   It contains no tab navigable elements in it.
*   **Shift Tab**
    *   As with other keyboard conventions described here, the Shift Tab has the effect of moving the focus up rather than down and follows the same conventions as described for the modal and non-modal Tab key above.
*   **Enter**
    *   Activates the element in the Popup Help that has input focus, if applicable, then dismisses the popup.
        *   Input focus should be placed on the appropriate element after the user presses the Enter key.
            *   The appropriate place to move input focus to will not always be the parent element the Popup Help was called by.
        *   Nothing occurs if input focus is on an element that has no associated action.
*   **F6**
    *   In the non-modal instance, the F6 key can be used to move focus between the application and the open non-modal window. This is also the behavior described in [Dialog (Non-Modal)](#dialognonmodal) above.

* * *

104.  ## <a name="radiobutton">Radio Button</a>

Example: An option in single-select list ([ARIA Radio](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#radio)). A group of radio controls ([ARIA Radiogroup](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#radiogroup)).

*   **Tab key** will enter the radio group.
    *   When tabbing into a group focus goes to the selected button. If none is selected it goes to the first button in the group unless you are shift tabbing, which goes to the last button in the group. Or in ARIA it can go to the radio group. HTML does not have a radio group.
    *   Tab again will exit the radio group.
*   **Down/Right** moves forward in the group.
*   **Up/Left** moves backwards in the group
    *   When the arrow moves focus, the button is selected.
*   **Down/Right arrow** at bottom should wrap to beginning of the set
*   **Up/Left arrow** at top should wrap to end of the set
*   **Space bar** is a toggle selected/unselected.
*   **Control Arrow** moves through the options without updating content or selecting the button.

* * *

108.  ## <a name="richtext">Rich Text Editor</a>

Example: Inputs that allow free-form text as their value ([ARIA Textbox](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#textbox)).

*   **Note:** The edit control is provided by the browser. The edit control provides the keyboard support for navigating, adding, removing and selecting text so that behavior is not defined by the DHTML Style Guide.
*   **Note:** The browser should also provide a keyboard mechanism for navigating into and out of the edit control. Within most browsers the edit control is put into the tab order of the page and can be navigated into, out of, and through using the tab and shift-tab keys like any standard form control.
*   **Note:** A rich text editor widget needs to provide a user interface for interacting with the browser provided edit control. Interaction between the user interface and editor is defined here assuming that a toolbar is used.
*   **Tab and Shift-Tab** If not provided by the browser, the rich text editor widget must provide a keyboard mechanism to move into and out of the edit control. Tab and shift-tab are the recommended keystrokes. The toolbar or other user interface component associated with the editor is placed in the tab order immediately before the editor. To set an attribute on text within the edit control the user sets focus into the edit control, moves the insertion point, selects text and presses shift-tab to move focus from the editor back to the toolbar. The user navigates through the toolbar (see toolbar behavior) to a desired attribute and invokes that attribute. When an attribute is invoked, that attribute is applied to the selected text in the editor and focus moves back into the editor at the previous insertion point with the selection intact.
*   **Options:**
    *   Rather than using shift-tab to move focus from within the editor to the toolbar, another key combination could be used (alt-up arrow, ctrl-shift-letter, etc.). This would eliminate the need to put the user interface control (in this example a toolbar) into the tab order immediately before the editor component. However, there are drawbacks to using a different keystroke to navigate to the user interface:
        1.  It is not as "discoverable" as relying on the standard tab/shift-tab behavior;
        2.  It is difficult to find key combinations which are not already captured by the browser or assistive technology.
        3.  Focus could stay within the toolbar after the user invokes an attribute. The user would then have to press an additional key to move focus back into the editor. This would allow multiple attributes to be set on the current selection without having to return back to the user interface but it would add an extra key sequence after setting just a single attribute. Requiring a keystroke to move focus back into the editor would also require modifying the toolbar behavior to intercept this keystroke and to know how to set focus back to the component (the editor) that the toolbar is associated with.
*   **Note:** Optionally, if the developer wishes to provide the ability to insert a tab into the document, it is recommended one of the following methods be used.
    *   Provide indent and outdent buttons in the menu. Keyboard shortcuts to the buttons should be **Control M** for indent and **Control Shift M** for outdent.
    *   Provide a button in the menu to toggle the use of Tab between the two modes. If this button is used, then **Control M** is recommended as a keyboard shortcut to toggle the button.

* * *

112.  ## <a name="slider">Slider</a>

Example: A user input where the user selects a value from within a given range.

A slider represents the current value and range of possible values via the size of the slider and position of the thumb. It is typically possible to add or subtract to the value by using directional keys such as arrow keys ([ARIA Slider](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#slider)).

*   **Right and Up Arrows** increase the value of the slider.
*   **Left and Down Arrows** decrease the value of the slider.
*   **Home and End** move to the minimum and maximum values of the slider.
*   **Tab** into and out of the slider.
*   **Page Up and Page Down** optionally increment or decrement the slider by a given amount.
*   **Note:** Focus is placed on the slider. (The visual object that the mouse user would move, also known as the thumb.)
*   **Note:** Localization for right to left languages may wish to reverse the left and right arrows.

* * *

117.  ## <a name="slidertwothumb">Slider (Multi-Thumb)</a>

Example: This three thumb slider shows a histogram of the range of colors in a photo. Moving the end sliders chops out the dark and light areas while the middle thumb shifts the brightness of the overall image lighter or darker ([ARIA Slider](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#slider)).  
![Screen shot shows 3 thumb slider.](https://web.archive.org/web/20130127004544im_/http://dev.aol.com/images/slider1.bmp)

This is a four thumb slider. Like the previous one we can compress the range of colors by modifying the end points but this one has two middle thumbs which does something magic that as a non-artist I can't really describe. Something to do with how many degrees around the color wheel the palette is shifted, or something.  
![Screen shot shows 4 thumb slider.](https://web.archive.org/web/20130127004544im_/http://dev.aol.com/images/slider2.bmp)

*   **Tab** to the first slider thumb.
*   **Second tab** moves to next slider thumb.
*   **Third tab** moves to the next slider thumb or if there are no more, it moves to the next tab stop on the page.
*   **Shift-tab** moves backwards through the tabs.
*   **With focus on a thumb:** Same as [Slider](#slider) above.
    *   **Right and Up Arrows** increases the value of the slider constrained by the value of the other thumb.
    *   **Left and Down** Arrows decrease the value of the slider constrained by the value of the other thumb.
    *   **Home and End** move to the minimum and maximum values of the slider constrained by the value of the other thumb.
    *   **Page Up and Page Down** optionally increment or decrement the slider by a given amount, constrained by the value of the other thumb.
*   **Note:** Focus is placed on one of the thumbs of the slider.
*   **Note:** All thumbs are in the tab order.
*   **Note:** Localization for right to left languages may wish to reverse the left and right arrows.
*   **Note:** If the current value of a slider crosses over one of the other sliders, the tab order remains the same. Example. If a high range slider is moved so that its current value is below the current value of a low range slider, the thumb will visually appear to be before the low range slider. This should not change the tab order of the slider.

* * *

122.  ## <a name="spinbutton">Spinbutton</a>

A form of range that expects a user to select from amongst discrete choices ([ARIA Spinbutton](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#spinbutton)).

A spinbutton typically allows the user to select from the given range through the use of an up and down button on the keyboard. Visibly, the current value is incremented or decremented until a maximum or minimum value is reached.

*   **Right and Up Arrows** increase the value.
*   **Left and Down Arrows** decrease the value.
*   **Home and End key** move to the maximum or minimum values
*   **Optional Page Up and Page Down** incrementally increase or decrease the value
*   **Tab key** moves into and out of the widget
*   **Note:** Focus should remain on the edit field
*   **Note:** Localization for right to left languages may wish to reverse the left and right arrows.

* * *

127.  ## <a name="tabpanel">Tab Panel</a>

Example: A container for the resources associated with a tab ( [ARIA Tabpanel](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#tabpanel)).

Commentary: the aria-expanded state is used to distinguish between an Accordion panel's expanded vs. collapsed state. An AT should be sensitive to aria-expanded, and relay it meaningfully to the user. Here are some role/state combinations and their meaning:

*   (role=tablist aria-multiselectable=true) is an Accordion
*   (role=tablist aria-multiselectable=false) is a Tab Panel
*   (role=tablist aria-multiselectable=true) and (focus on role=tab aria-expanded=true) is an Accordion Header whose panel is expanded
*   (role=tablist aria-multiselectable=false) and (focus on role=tab aria-expanded=true) is a Tab whose panel is expanded
*   (role=tablist aria-multiselectable=true) and (focus on role=tab aria-expanded=false) is an Accordion Header whose panel is collapsed.

*   **Down Arrow/Right Arrow**
    *   When focus is on the tab or accordion header, a press of down/right will move focus to the next logical accordion Header or Tab page.
    *   When focus reaches the last header/tab page, further key presses will have optionally wrap to the first header
    *   In the case of a tab the corresponding tab panel will activate
*   **Up Arrow/Left Arrow**
    *   When focus is on the tab or accordion header, a press of up/left will move focus to the previous logical accordion Header or Tab page.
    *   When focus reaches the first header/tab page, further key presses will optionally wrap to the first header.
    *   In the case of a tab the corresponding tab panel will activate.
*   **Enter/Space**
    *   When focus is on an Accordion Header, this keystroke toggles the expansion of the corresponding panel.
        *   If collapsed, the panel is expanded, and its aria-expanded state is set to 'true'.
        *   If expanded, the panel is collapsed and its aria-expanded state is set to 'false'.
    *   When focus is on a Tab in a Tab Panel, this keystroke has no effect.
        *   Note: Tab Panel panels are auto-expanded when their corresponding Tab receives focus, and auto-collapsed when focus moves to another Tab.
        *   In this case, the behaviour of depends on the role of the interactive element, and is defined elsewhere in this document (cf., Menu).

*   **Control Up Arrow/Left Arrow**
    *   Moves focus from anywhere in the accordion content or tab page to its associated accordion Header or Tab respectively.
    *   Note: This key combination is useful on browsers which already implement Control PageUp/PageDown for other functions such as switching browser tabs.
*   **Control PageUp**
    *   When focus is inside of a tab panel / accordion pane, pressing ctrl-pageup moves focus to the tab or accordion header of the previous tab/accordion pane.
    *   When focus is in the first tab panel in the tab list or the first accordion header content, pressing ctrl-pageup will optionally move focus to the last tab in the tab list or the last accordion header.
    *   In the case of being in a tab panel the previous pane will be activated. In the case of an accordion focus will simply move to the header and will require Enter/space to expand/collapse the accordion pane.
*   **Control PageDown**
    *   When focus is inside of a tab panel / accordion pane, pressing ctrl-pagedown moves focus to the tab or accordion header of the next tab/accordion pane.
    *   When focus is in the last tab panel in the tab list or the last accordion header content, pressing ctrl-pagedown will optionally move focus to the first tab in the tab list or the first accordion header.
    *   In the case of being in a tab panel the next pane will be activated. In the case of an accordion focus will simply move to the header and will require Enter/space to expand/collapse the accordion pane.
*   **Tab**
    *   When focus is on an Accordion Header / Tab, a TAB keystroke will move focus in the following manner:
        1.  If interactive glyphs or menus are present in the Accordion Header / Tab, focus will move to each of these glyphs or menus in order.
        2.  When the corresponding Tab or Accordion panel is expanded (its aria-expanded state is 'true'), then focus moves to the first focusable element in the panel. (Note: for Tab Panel, the corresponding panel is expanded automatically when focus is on the Tab).
        3.  If the Accordion panel is collapsed (its aria-expanded state is 'false', or missing), OR, when the last interactive element of an expanded Tab or Accordion panel is reached, the next TAB keystroke will move focus as follows:
            *   If multi-select is enabled and a subsequent Accordion panel is already expanded, focus will move to the first focusable element in this subsequent panel.
            *   If multi-select is enabled and no subsequent Accordion panel is expanded, OR, if multi-select is disabled, focus will move to the first focusable element outside the Accordion or Tab Panel component.
*   **Shift Tab** Generally the reverse of Tab
*   **Shift F10** See Global Section
*   **Alt Del**
    *   When deletion is allowed, with focus anywhere within the tab panel or tab, pressing alt-del will delete the current tab and tab panel from the tabbed interface control. If additional tabs remain in the tabbed interface, focus goes to the next tab in the tab list. If no additional tabs remain, then focus moves to the last place that held focus in the previous tab panel.
    *   An alternative to providing a keystroke to close a tab is to provide a context menu that is associated with the tab title. When focus is on the tab, pressing shift-F10 or pressing the right mouse button will open a context menu with the close choice.
    *   This would be unlikely to be implemented for an accordion but could be implemented if required in a similar manner.
    *   A warning should be give to the user before allowing the delete to occur.
*   **Esc** See Global button/menu actions

* * *

134.  ## <a name="toolbar">Tool Bar</a>

Example: A collection of commonly used functions represented in compact visual form ([ARIA Toolbar](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#toolbar)).

The toolbar is often a subset of functions found in a menubar, designed to reduced user effort in using these functions.

*   **Tab** moves focus to the first enabled toolbar button.
*   **Tab Again** moves focus out of the toolbar
*   **Left and Right Arrow** keys navigate to the enabled buttons in the toolbar
*   **Note:** Direction may need to be adjusted for Right to Left languages
*   **Note:** There has been a lot of discussion around disabled buttons. The question is, "Should they be focusable or not"? Visually, these are grayed out and are not placed in the tab order, but the question remains how does a screen reader user discover these buttons if they are not focusable? Generally there are a number of ways this can be handled.
    1.  In software applications like MS word, the toolbars are not reachable by the keyboard user, but the features are available on one of the drop down menus.
    2.  A user could be asked to set a preference to indicate they want the disabled buttons surfaced.
    3.  The can be disabled and not discoverable until they are activated. (This is the way tool bars currently work)
    4.  They can be focusable, but read by the screen reader as disabled.

* * *

139.  ## <a name="tooltip">Tooltip Widget</a>

Example: A popup that displays a description for an element when a user passes over or rests on that element. Supplement to the normal tooltip processing of the user agent ([ARIA Tooltip](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#tooltip)).

[Complete proposal from Earl Johnson](https://web.archive.org/web/20130127004544/http://dev.aol.com/downloads/kbd-nav--popup-tool-bubble-022808.html)

The tooltip widget should popup automatically when the user gives input focus to the widget or element it is tied to. The tooltip widget can be dismissed by pressing the ESC key or by other methods noted below. The Tooltip Widget differs from the [Dialog (Tooltip)](#dialogtooltip) in that it does not receive focus at any time.

*   **ESC:** Dismisses the Tooltip.
*   **Note:** The trigger element to which the tooltip is attached, e.g., a link, should never actually lose input focus.
*   **Note:** If the tooltip is invoked when the trigger element gets focus, then it should be dismissed when it no longer has focus (onBlur). If the tooltip is invoked with mouseIn, then it should be dismissed with a mouseOut.
*   **Note:** If more then one widget uses the same keys, e.g., Esc, then they should be handled in a Last In First Out (LIFO) manner.

* * *

145.  ## <a name="treeview">Treeview</a>

Example: A form of a list having groups inside groups, where sub trees can be collapsed and expanded ([ARIA Tree](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#tree)).

*   **Up and down arrow** keys move between visible nodes
*   **Left arrow** key on an expanded node closes the node
*   **Left arrow** key on a closed or end node moves focus to the node's parent
*   **Right arrow** key expands a closed node, moves to the first child of an open node, or does nothing on an end node.
*   **Enter key** performs the default action on end nodes.
*   **Typing a letter (printable character) key** moves focus to the next instance of a visible node whose title begins with that printable letter.
*   **Home key** moves to the top node in the tree view
*   **End key** moves to the last visible node in the tree view
*   **Ctrl Arrow** to an item with the keyboard focuses the item (but does not select it). Previous selections are maintained.
*   **Ctrl Spacebar** with focus on an item toggles the selection of the item
*   **Shift UpArrow** - Extends selection up one node
*   **Shift DownArrow** - Extends selection down one node
*   **Shift Home** - Extends selection up to the top-most node
*   **Shift PageDown** - Extends selection down to the last node
*   ***(asterisk)** on keypad - Expands all nodes
*   **Note:** It may also be advisable to allow more then 1 printable character to be typed. In this case focus is moved to the next instance of a visible node whose title matches the string typed. Generally when this is used, it includes a timer which will reset the string thus allowing another search. For this reason, this technique is not recommended unless the user may set a preference to increase the time allowed.

* * *

149.  ## <a name="windowsplitter">Window Splitter</a>

Example: A splitter is a visible separator between sections of a Window which can be used to modify the size of the panes.

*   **Tab** Like other widgets, the tab key is used to move focus to the splitter. It should appear in the normal tab order of the page. A second tab will move focus to the next tabbable item on the page.
*   **Left and Right Arrow** In the case of a vertical splitter these keys will move the splitter to the left and to the right.
*   **Up and Down Arrow** In the case of a horizontal splitter these keys will move the splitter up and down.
*   **End** Moves splitter to the maximum size of the region.
*   **Home**Moves splitter to the minimum size of the region
*   **Enter** Restore splitter to previous position (undo Home or End)
*   **F6** Optionally is recommended to rotate through the window panes.
*   **Control F6** Optionally brings focus directly to the splitter. Pressing Control F6 again would rotate forward through additional splitters located on the page.
*   **Shift Control F6** Optionally reverses the direction rotating backwards through additional splitters located on the page.

*   **Note:** Fixed size splitter simply omits implementation of the arrow keys
*   **Note:** The group recommends unique naming of the window splitter to avoid the confusion that could be created by multiple splitters located on the same window.
*   **Note:** The group recommends a splitter default position restore option to be available in a contextual menu.

* * *

153.  ## <a name="wizard">Wizard</a>

Example: A set of pages that create a signup wizard.

*   A Wizard can be done in several ways. Any are valid
    1.  Method 1: Like a [Tool Bar](#toolbar)
    2.  Method 2: Controls as Default Actions
        *   **ESC** cancels the wizard.
        *   **Return or Enter** invokes the "next" action; If the last page, it invokes "finish"
    3.  Method 3: Hot Keys
        *   **Control Alt N** next, finish
        *   **Control Alt P** previous
        *   **Escape** cancel, exit without saving
        *   **Control Alt R** reset current page to default settings
        *   **Control Alt S** save and exit
        *   **Note:** Letters should be localized.
    4.  Method 4: Like a [Dialog](#dialognonmodal)

* * *

## <a name="global">Global Recommendations</a>

The following may apply to some or all widgets.

*   **Control Z** Optionally a developer may choose to implement undo functionality as needed. It is recommended that Control Z be used.
*   **Control Y** Optionally a developer may choose to implement redo functionality as needed. It is recommended that Control Y be used.
*   **Control C** Copies to clipboard
*   **Control V** Pastes from clipboard
*   **Control X** Copies to clipboard and cuts
*   **Shift F10** is used to bring up an associated [Popup Menu](#popupmenu)
*   **Widgets within Widgets** The general navigation model is for a user to tab to a widget, interact with the controls in that widget and then tab to move focus to the next widget in the tab order. By extension, when the construct of a widget contains another widget, tab will move focus to the contained widget because it is the next item in the tab order. This continues down the layers of widgets until the last widget is reached. For example: We have two widgets A and B on a page. Widget A contains within it Widget C and Widget C contains within it Widget D. When tabbing, focus would land on Widget A, then another tab would focus on C and then another tab would focus on widget D. Because D is the the last widget in C and C is the last widget in A one more tab would move focus to B.
*   **Bidirectional Typography** Many of the widget keyboard recommendations include directional navigation which assumes a left to right reading order. Implementors need to be aware that these relative directions will need to be reversed when the language typography runs from right to left.

* * *

## <a name="gap">Gap Analysis</a> (Styleguide vs [ARIA Roles](https://web.archive.org/web/20130127004544/http://www.w3.org/WAI/PF/aria/#parentrole))

<table border="1">

<tbody>

<tr>

<th>ARIA Role</th>

<th>Styleguide</th>

<th>Definition</th>

</tr>

<tr>

<td>Alert</td>

<td>[Alert](#alert)</td>

<td>A message with important information.</td>

</tr>

<tr>

<td>Alert Dialog</td>

<td>[Dialog (Modal)](#dialogmodal), [Dialog (Non-Modal)](#dialognonmodal), [Dialog (Tooltip)](#dialogtooltip)</td>

<td>A separate window (may be simulated) with an alert, where initial focus goes to the window or a control within it.</td>

</tr>

<tr>

<td>Application</td>

<td>N/A</td>

<td>A software unit executing a set of tasks for its users.</td>

</tr>

<tr>

<td>Article</td>

<td>[Landmark](#landmarks)</td>

<td>Represents a section of a page consisting of a composition forming an independent part of a document, page, or site.</td>

</tr>

<tr>

<td>Banner</td>

<td>[Landmark](#landmarks)</td>

<td>A region that contains the prime heading or internal title of a page.</td>

</tr>

<tr>

<td>Button</td>

<td>[Button](#button)</td>

<td>Allows for user-triggered actions</td>

</tr>

<tr>

<td>Checkbox</td>

<td>[Checkbox](#checkbox)</td>

<td>A control that has three possible values, (true, false, mixed).</td>

</tr>

<tr>

<td>Columnheader</td>

<td>N/A</td>

<td>A table cell containing header information for a column.</td>

</tr>

<tr>

<td>Combobox</td>

<td>[Combobox](#combobox)</td>

<td>Combobox is a presentation of a select, where users can type to select an item.</td>

</tr>

<tr>

<td>Complementary</td>

<td>[Landmark](#landmarks)</td>

<td>Any section of the document that supports but is separable from the main content, but is meaningful on its own even when separated from it.</td>

</tr>

<tr>

<td>Contentinfo</td>

<td>N/A</td>

<td>Meta information which applies to the first immediate ancestor whose role is not presentation.</td>

</tr>

<tr>

<td>Definition</td>

<td>N/A</td>

<td>A definition of a term or concept.</td>

</tr>

<tr>

<td>Description</td>

<td>N/A</td>

<td>Descriptive content for a page element which references this element via describedby.</td>

</tr>

<tr>

<td>Dialog</td>

<td>[Dialog (Modal)](#dialogmodal), [Dialog (Non-Modal)](#dialognonmodal), [Dialog (Tooltip)](#dialogtooltip)</td>

<td>A dialog is a small application window that sits above the application and is designed to interrupt the current processing of an application in order to prompt the user to enter information or require a response.</td>

</tr>

<tr>

<td>Directory</td>

<td>[Landmark](#landmarks)</td>

<td>A list of references to members of a single group.</td>

</tr>

<tr>

<td>Document</td>

<td>N/A</td>

<td>Content that contains related information, such as a book.</td>

</tr>

<tr>

<td>Grid</td>

<td>[Tree Grid](#treegrid), [Grid](#grid)</td>

<td>A grid contains cells of tabular data arranged in rows and columns (e.g., a table).</td>

</tr>

<tr>

<td>Gridcell</td>

<td>[Tree Grid](#treegrid), [grid](#grid)</td>

<td>A gridcell is a table cell in a grid. Gridcells may be active, editable, and selectable. Cells may have relationships such as controls to address the application of functional relationships.</td>

</tr>

<tr>

<td>Group</td>

<td>[Landmark](#landmarks)</td>

<td>A group is a section of user interface objects which would not be included in a page summary or table of contents by an assistive technology. See region for sections of user interface objects that should be included in a page summary or table of contents.</td>

</tr>

<tr>

<td>Heading</td>

<td>[Landmark](#landmarks)</td>

<td>A heading for a section of the page.</td>

</tr>

<tr>

<td>Img</td>

<td>N/A</td>

<td>An img is a container for a collection elements that form an image.</td>

</tr>

<tr>

<td>Link</td>

<td>[Link](#link)</td>

<td>Interactive reference to a resource (note, that in [XHTML] 2.0 any element can have an href attribute and thus be a link)</td>

</tr>

<tr>

<td>List</td>

<td>[Listbox](#listbox)</td>

<td>Group of small items.</td>

</tr>

<tr>

<td>Listbox</td>

<td>[Listbox](#listbox)</td>

<td>A list box is a widget that allows the user to select one or more items from a list. Items within the list are static and may contain images.</td>

</tr>

<tr>

<td>Listitem</td>

<td>[Listbox](#listbox)</td>

<td>A single item in a list.</td>

</tr>

<tr>

<td>Log</td>

<td>[Landmark](#landmarks)</td>

<td>A region where new information is added and old information may disappear such as chat logs, messaging, game log or an error log. In contrast to other regions, in this role there is a relationship between the arrival of new items in the log and the reading order. The log contains a meaningful sequence and new information is added only to the end of the log, not at arbitrary points.</td>

</tr>

<tr>

<td>Main</td>

<td>[Landmark](#landmarks)</td>

<td>Main content in a document.</td>

</tr>

<tr>

<td>Marque</td>

<td>N/A</td>

<td>A marquee is used to scroll text across the page.</td>

</tr>

<tr>

<td>Math</td>

<td>N/A</td>

<td>Content that represents a mathematical expression.</td>

</tr>

<tr>

<td>Menu</td>

<td>[Menu](#menu), [Menu Button](#menubutton), [PopupMenu](#popupmenu)</td>

<td>Offers a list of choices to the user.</td>

</tr>

<tr>

<td>Menubar</td>

<td>[Menu](#menu), [Menu Button](#menubutton), [PopupMenu](#popupmenu)</td>

<td>A menubar is a container of menu items. Each menu item may activate a new sub-menu. Navigation behavior should be similar to the typical menu bar graphical user interface.</td>

</tr>

<tr>

<td>Menuitem</td>

<td>[Menu](#menu), [Menu Button](#menubutton), [PopupMenu](#popupmenu)</td>

<td>A link in a menu. This is an option in a group of choices contained in a menu.</td>

</tr>

<tr>

<td>Menuitemcheckbox</td>

<td>[Checkbox](#checkbox)</td>

<td>Defines a menuitem which is checkable (tri-state).</td>

</tr>

<tr>

<td>Menuitemradio</td>

<td>[Radio Button](#radiobutton)</td>

<td>Indicates a menu item which is part of a group of menuitemradio roles.</td>

</tr>

<tr>

<td>Navigation</td>

<td>[Listbox](#listbox)</td>

<td>A collection of links suitable for use when navigating the document or related documents.</td>

</tr>

<tr>

<td>Note</td>

<td>N/A</td>

<td>The content is parenthetic or ancillary to the main content of the resource.</td>

</tr>

<tr>

<td>Option</td>

<td>[Listbox](#listbox)</td>

<td>A selectable item in a list represented by a select.</td>

</tr>

<tr>

<td>Presentation</td>

<td>N/A</td>

<td>An element whose role is presentational does not need to be mapped to the accessibility API.</td>

</tr>

<tr>

<td>Progressbar</td>

<td>N/A</td>

<td>Used by applications for tasks that take a long time to execute, to show the execution progress.</td>

</tr>

<tr>

<td>Radio</td>

<td>[Radio Button](#radiobutton)</td>

<td>A radio is an option in single-select list. Only one radio control in a radiogroup can be selected at the same time.</td>

</tr>

<tr>

<td>RadioGroup</td>

<td>[Radio Button](#radiobutton)</td>

<td>A group of radio controls.</td>

</tr>

<tr>

<td>Region</td>

<td>N/A</td>

<td>Region is a large perceivable section on the web page.</td>

</tr>

<tr>

<td>Row</td>

<td>[Tree Grid](#treegrid), [Grid](#grid)</td>

<td>A row of table cells.</td>

</tr>

<tr>

<td>Rowheader</td>

<td>[Grid](#grid)</td>

<td>A table cell containing header information for a row.</td>

</tr>

<tr>

<td>Search</td>

<td>[Auto Complete](#autocomplete) & [Landmark](#landmarks)</td>

<td>The search tool of a web document.</td>

</tr>

<tr>

<td>Separator</td>

<td>N/A</td>

<td>A line or bar that separates and distinguishes sections of content.</td>

</tr>

<tr>

<td>Slider</td>

<td>[Slider, Slider (Multi-Thumb)](#slider)</td>

<td>A user input where the user selects an input in a given range. This form of range expects an analog keyboard interface.</td>

</tr>

<tr>

<td>Spinbutton</td>

<td>[Spinbutton](#spinbutton)</td>

<td>A form of Range that expects a user selecting from discrete choices.</td>

</tr>

<tr>

<td>Status</td>

<td>[Landmark](#landmarks)</td>

<td>This is a container for process advisory information to give feedback to the user.</td>

</tr>

<tr>

<td>Tab</td>

<td>[Tab Panel](#tabpanel)</td>

<td>A header for a tabpanel.</td>

</tr>

<tr>

<td>Tablist</td>

<td>[Tab Panel](#tabpanel)</td>

<td>A list of tabs, which are references to tabpanels.</td>

</tr>

<tr>

<td>Tab Panel</td>

<td>[Tab Panel](#tabpanel)</td>

<td>Tabpanel is a container for the resources associated with a tab.</td>

</tr>

<tr>

<td>Textbox</td>

<td>[Rich Text Editor](#richtext)</td>

<td>Inputs that allow free-form text as their value.</td>

</tr>

<tr>

<td>Timer</td>

<td>N/A</td>

<td>A numerical counter which indicates an amount of elapsed time from a start point, or the time remaining until an end point.</td>

</tr>

<tr>

<td>Toolbar</td>

<td>[Tool Bar](#toolbar)</td>

<td>A toolbar is a collection of commonly used functions represented in compact visual form.</td>

</tr>

<tr>

<td>Tooltip</td>

<td>[Tooltip Widget](#tooltip)</td>

<td>A popup that displays a description for an element when a user passes over or rests on that element. Supplement to the normal tooltip processing of the user agent.</td>

</tr>

<tr>

<td>Tree</td>

<td>[Treeview](#treeview)</td>

<td>A form of a list having groups inside groups, where sub trees can be collapsed and expanded.</td>

</tr>

<tr>

<td>Treegrid</td>

<td>[Tree Grid](#treegrid), [Treeview](#treeview)</td>

<td>A grid whose rows can be expanded and collapsed in the same manner as for a tree.</td>

</tr>

<tr>

<td>Treeitem</td>

<td>[Tree Grid](#treegrid), [Treeview](#treeview)</td>

<td>An option item of a tree. This is an element within a tree that may be expanded or collapsed</td>

</tr>

</tbody>

</table>

* * *

<a name="participants"></a>

# Participants and Contributors

1.  Tom Wlodkowski, AOL (Chair)
2.  Chris Blouch, AOL
3.  Tim Boland, NIST
4.  David Bolter, Adaptive Technology Resource Centre, Faculty of Information, University of Toronto
5.  Sally Cain, RNIB
6.  Amy Chen, Oracle
7.  Donald F. Evans, DeQue Systems
8.  Becky Gibson, IBM
9.  Al Gilman, W3C
10.  Jon Gunderson, Ph.D. University of Illinois at Urbana-Champaign
11.  Kenny Johar
12.  Oliver Keim, SAP
13.  Aaron M. Leventhal
14.  James Nurthen, Oracle
15.  Sailesh Panchang, DeQue Systems
16.  Lisa Pappas, SAS
17.  David Poehlman
18.  Earl Johnson, SUN
19.  Hadi Bargi Rangin, UIUC
20.  Gregory J. Rosmaita, UBATS
21.  Joseph Scheuhammer, Ph.D. Adaptive Technology Resource Centre, Faculty of Information, University of Toronto.
22.  Stefan Schnabel, SAP
23.  Richard Schwerdtfeger, IBM
24.  Victor Tsaran, Yahoo