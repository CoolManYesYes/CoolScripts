Here is the documentation with the code properly wrapped in code blocks so you can easily copy it:


---

UI Library Documentation

The UI Library provides an easy way to create a tabbed user interface (UI) with draggable support for both PC and Mobile platforms. This library includes features like tabs, buttons, toggles, sliders, and a dropdown for additional tabs when the limit is reached.


---

1. Library Setup

To use the library, include it in your script. It can be used for both PC and Mobile devices.

local UILibrary = require(path_to_uilibrary)


---

2. Creating a Window

You don't need to create the main window manually. The library automatically creates a window (ScreenGui) and attaches it to the player's CoreGui.


---

3. Draggable Window

The window (represented by MainFrame) is draggable by both mouse (for PC) and touch (for mobile). You can drag the window by clicking or touching on the TabBar (the top bar).


---

4. Tabs

Tabs can be created using the CreateTab function. When the number of tabs exceeds the defined TabLimit, the additional tabs are moved to a Dropdown that can be accessed by clicking on the “More” button.

Creating a Tab

local tab = UILibrary:CreateTab("Tab Name")

Tab Features

Tab Button: This button allows switching between tabs.

Tab Frame: The content associated with each tab. Only one tab frame is visible at a time.



---

5. Adding Elements to Tabs

Within each tab, you can add various elements such as buttons, labels, toggles, and sliders.

Add a Button

tab:AddButton("Button Text", function()
    print("Button clicked!")
end)

Add a Label

tab:AddLabel("This is a label")

Add a Toggle

tab:AddToggle("Enable Feature", function(state)
    print("Toggle State:", state)
end)

state will be true if the toggle is on, and false if off.


Add a Slider

tab:AddSlider("Adjust Volume", 0, 100, 50, function(value)
    print("Slider Value:", value)
end)

The slider will allow the user to select a value between min and max. The default value is the initial value of the slider.



---

6. Dropdown for Extra Tabs

When the number of tabs exceeds the TabLimit, the library will automatically display a Dropdown with a “More” button at the top of the window. Clicking on this will reveal extra tabs.


---

7. Tab Limit

The TabLimit is set to 5 by default. You can change this limit if needed by modifying the variable.


---

8. Example Usage

Here is an example of how you would use the library to create a window with two tabs, one with a button and the other with a toggle:

local UILibrary = require(path_to_uilibrary)

local tab1 = UILibrary:CreateTab("First Tab")
tab1:AddButton("Click Me", function()
    print("Button was clicked!")
end)

local tab2 = UILibrary:CreateTab("Second Tab")
tab2:AddToggle("Enable Feature", function(state)
    if state then
        print("Feature Enabled")
    else
        print("Feature Disabled")
    end
end)


---

9. Mobile and PC Compatibility

The window is draggable on both PC (via mouse drag) and Mobile (via touch drag).

The UI supports both input types, making it fully mobile-friendly.



---

10. Customization Options

TabLimit: The maximum number of tabs before a dropdown appears. This is set to 5 by default but can be customized.


local TabLimit = 5 -- Modify this value to change the tab limit

Visual Customization: You can modify the BackgroundColor3, TextColor3, TextSize, Font, and other properties of buttons, labels, toggles, and sliders as needed.



---

11. Functions and Events

CreateTab(name: string)

Creates a new tab with the given name.

name: The name of the tab.


AddButton(text: string, callback: function)

Adds a button to the tab with the given text. The callback function is triggered when the button is clicked.

text: The text displayed on the button.

callback: A function that is called when the button is clicked.


AddLabel(text: string)

Adds a label to the tab with the given text.

text: The label text.


AddToggle(text: string, callback: function)

Adds a toggle (on/off) button to the tab. The callback function is triggered when the toggle is clicked, with true if toggled on, and false if toggled off.

text: The text displayed on the toggle button.

callback: A function that receives the toggle state.


AddSlider(text: string, min: number, max: number, default: number, callback: function)

Adds a slider to the tab. The callback function is called when the slider value changes.

text: The text displayed near the slider.

min: The minimum value of the slider.

max: The maximum value of the slider.

default: The default value of the slider.

callback: A function that receives the slider value.



---

Conclusion

This library is a straightforward and easy-to-use solution for creating a tabbed UI in Roblox games with dragging support for both PC and Mobile. You can expand it further by adding more customization options, such as more UI elements and specific event listeners.

