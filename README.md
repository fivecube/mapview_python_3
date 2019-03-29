# mapview_python_3
### There were numerous problems with using mapview in kivy in python3.
#### These 2 are the most frustrating-:
1)Lambda syntax error due to recent change in tuple unpacking syntax in python 3.
2)PyInstaller does not love Packages poorly designed by using sys to change paths or we can say the "Hidden Imports".
So basically the whole point of using mapview in kivy was to make a application and if Pyinstaller does not recognise it, Then you are in trouble.
## But Here's the solution.
>>So this is basically a workaround idea which worked very well for me.
>>So basically I croped out all the code line by line from different folders of their original package and make it into a single .py file which >>you can download and just use it by copy pasting in your main python file on top of all your code.

Here's an example of making an app and placing a marker.
```from kivy.app import App


class MainApp(App):
    def build(self):
        self.title = "Your_app"
        object = MapView(zoom=4, lat=26, lon=75)
        m = MapMarker(lat=26, lon=75)
        object.add_marker(m)
        return object


if __name__ == "__main__":
    MainApp().run()
  ```

![Alt text](example_run.PNG?raw=true "How it displayed where I Live!")


