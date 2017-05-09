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

### Day 4: April 21, 2017

**Today's Progress**: Started implementation of a custom control.

**Thoughts** Despite having the time, my motivation was a bit lacking today. It likely has to do with the fact that it was a Friday evening, and those tend to be my least productive time of the week. Today I learned about custom controls in iOS. A custom control is a specialized type of view (specifically, an instance of the UIControl class or one of its subclasses) that responds to user input. In the process of creating this custom control, I'm also learning how to generate view elements programatically in addition to doing it from the storyboard. I look forward to continuing on this progress tomorrow.

### Day 5: April 22, 2017

**Today's Progress**: Stil working on custom control to implement star rating.

**Thoughts** Unfortunately, it was another sluggish day. Still getting myself mentally trained to do work on weekends. Today I continued implementing the custom control for the star ratings. I learned how to connect the custom control properties from code to the Interface Builder via adding the @IBInspectable attribute to the properties. You have to also implement the didset() method on those properties to enable an update when someone changes their values in the Interface Builder. I also learned how to initialize an array in swift ( ... = [ArrayType]() ). Lastly, I learned how to enable the custom control to be displayed within the Interface Builder by adding the @IBDesignable attribute to the custom control class declaration.

### Day 6: April 23, 2017

**Today's Progress**: Finished the custom control to implement the star rating.

**Thoughts** The custom control portion of the Swift ios tutorial took a while, but I learned a lot of useful concepts. This is probably code I will need to come back and review on in the future. However, I did enjoy it and I think learning to make your own ios custom control is a very useful tool to have in your toolbox.

### Day 7: April 26, 2017 - Optionals and Unwrapping

**Today's Progress**: After a 2 day hiatus (thankfully it wasn't longer), I have resumed the challenge.! Today, I didn't write any code at all. However, I did spend time analyzing the code that I wrote while following the tutorial to implement the custom control rating buttons since there were a lot of Swift concepts that I did not quite understand. Thus, I spent my time today reading up on the Swift language. Here's what I learned. The "?" after a variable type declaration denotes a variable of the specified type that can have an optional value. This mean that at any given point during the execution of the program, the variable can be valueless (or nil). You can access the underlying value of an optional variable using the '!' operator at the end of the variable name. This is called "forced unwrapping." The exclamation mark effectively says, "I know that this optional definitely has a value; please use it." If you define an optional variable without providing a default value, the variable is automatically set to nil for you.

**Thoughts** Swift is very cool, and I am excited to learn more about this programming language.!

**Link(s) to work**

### Day 8: May 8, 2017 - Strong/Weak References and Refernce Cycles

**Today's Progress**: Unfortunately, I took another hiatus, but I am back at it, which is all that matters at this point. After a refresher on optionals, I started off reading about Automatic Reference Counting (ARC). Swift uses ARC to track and manage your app's memory usage. ARC automatically frees up the memory used by class instances when those instances are no longer needed. This basically performs a similar function as the garbage collectors in Java and C#. To make sure instances in use do not disappear (aka are deleted from memory), ARC tracks how many properties, constants, and vairables are currently referring to each class instance. ARC will not deallocate an instance as long as atleast one active strong reference to that instance still exists.

Whenever you assign a class instance to a property, constant, or variable, that property, constant, or variable makes a strong reference to the instance. The reference is called a “strong” reference because it keeps a firm hold on that instance, and does not allow it to be deallocated as long as that strong reference remains.

Knowing this, it appears that memory leaks occur when references to objects are not properly deallocated and objects continue to persist in memory well after they are no longer needed. This causes objects to crowd up the memory and ultimately results in a memory leak.

**Weak References**

A weak reference is a reference that does not keep a strong hold on the instance it refers to, and so does not stop ARC from disposing of the referenced instance. This behavior prevents the reference from becoming part of a strong reference cycle. ARC automatically sets a weak reference to nil when the instance that it refers to is deallocated.  Because weak references need to allow their value to be changed to nil at runtime, they are always declared as variables, rather than constants, of an optional type. You can check for the existence of a value in the weak reference, just like any other optional value, and you will never end up with a reference to an invalid instance that no longer exits.

Use a weak reference when the other instance has a shorter lifetime - that is, when the other instance can be deallocated first. For example, it is appropriate for an apartment to be able to have no tenant at some point in its lifetime, and so a weak reference to a tenant would be appopriate because when you deference the variable containing the strong reference to the tenant, there is only the weak reference remaining (which would be automatically derefereced by the ARC), thereby allowing the object to be deallocated.


**Thoughts** Swift is very cool, and I am excited to learn more about this programming language.!

**Link(s) to work** https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/AutomaticReferenceCounting.html#//apple_ref/doc/uid/TP40014097-CH20-ID55
