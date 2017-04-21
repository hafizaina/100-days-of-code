# 100 Days Of Code - Log

### Day 0: April 17, 2017

**Today's Progress**: Initial setup. Forked git repo.

**Thoughts:** Easy day.

### Day 1: April 18, 2017

**Today's Progress**: I worked on iOS development and added an image viewer to the app.

**Thoughts:** So far, things are going good. I am having fun learning iOS and Swift.

### Day 2: April 19, 2017
##### (delete me or comment me out)

**Today's Progress**: Worked on functionality to implement image picker for meal entry in the app.

**Thoughts**: I learned that in iOs there is a difference between views (of type UIView) and controls (of type UIControl which subclasses UIView). Views are simply dispayed items such as text and images. Controls, while being a subclass of view, are interactive entities within a content view. While implementing an image picker, I had a default image that the user has to tap in order to enable the image picker. However, an image is simply a view and not a control. With the use of a GestureRecognizer object, I was able to decorate the view object (UIImageView) with a gesture recognizer which recognizes a tap gesure, and therefore, I was able to transform the UIImageView view object into a control object.

### Day 3: April 20, 2017

**Today's Progress**: I've got the image picker working for the app.

**Thoughts** Short day. Started coding late. I implemented the 
imagePickerControllerDidCancel(_ picker: UIImagePickerController) & 
imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [String : Any]) function within the view controller that handles meal item creation. These methods are part of the UIImagePickerControllerDelegate class that were overridden by my view controller since it serves as a delegate to the image controller and thus extends that class. The first method deals with the scenario where a user cancels out of the image picker, and the second method deals with the scenario when a user picks an image via the image picker. I also learned about info.plist, which is a key-value property list where essential configuration information about the app is stored. I learned that starting with iOS 10+, the system must ask the user before accessing thier photo library. Therefore, you must provide a photo library usage description (by adding a new item line within the info.plist file). The description should explain why your app wants to access the photo library.

**Link(s) to work**
1. [Find the Longest Word in a String](https://www.freecodecamp.com/challenges/find-the-longest-word-in-a-string)
2. [Title Case a Sentence](https://www.freecodecamp.com/challenges/title-case-a-sentence)
