# Color.fromString

An important update !  From a Reddit user (pengo-san) that commented on my thread for this...
they found the following blog entry that you should read if you are needing more than what my solution offers.
https://nilcoalescing.com/blog/EncodeAndDecodeSwiftUIColor/


SwiftUI's Color object is not codable - and therefore not easy to store.  This makes it simple by allowing you to store a Color using Color.description and then recreating the Color using this function as an extension to Color

Simple to use...

Add this to any of your apps .swift files - outside of any structs or classes

Save a Color to a String using Color.description (this even works with the different Color.description obtained from ColorPicker and by using Color enums such as Color.Pink)
You can also manually create a color string using the format "#rrggbboo" where the initial # is required, then the rr, gg, bb and oo are hexadecimal numbers for Red, Green, Blue and Opacity components.

Recreate the Color from the stored String using Color.fromString()

Example...

var myColorString: String = "#C0C0C0FF"
var myColorObj: Color = .clear
var myPink: String = Color.pink.description
var pinkColorObj: Color = .clear

in code...
        myColorObj = Color.fromString(myColorString)    //Returns a Color that is gray (rgba = C0C0C0FF)
        pinkColorObj = Color.fromString(myPink)         //Returns a Color equal to Color.pink
      
you can now use a Color.description String in structs (and classes) and make the struct Codable...
you can also store Colors in CoreData as a string

Please feel free to make this better and share it with me !
