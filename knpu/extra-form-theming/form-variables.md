# Form Variables

The most common function that I use to render fields is [former's grill? 00:00:04]. That's in the actual form is the first argument. The second argument you pass at variables which is kind of a weird thing. What are these variables? Apparently one of the variables are your passes called Label. If you want to override the label, one way is with variables.

Let's try that with our sub-family. Let's pass the second argument which is an array, we'll say label, we'll say ... Taxonomic. Subfamily. Go back. Refresh. There it is. Okay, that's cool, so what else can we do inside of these variables? It also turns out that every field has a variable called ATTR, which is itself, an array. These are attributes that you want set on the widget, so the text area or the input.

For example, we can set class to Foo, and we can set disable to disable. Let's check out that. Refresh, and there we go, this is disabled. If we check out the widget, this slot, there is our extra Foo class. Awesome, so these variables give us a lot of control over how the fields render. It still does not answer my last question which is ... What are the variables that I could actually use on a field beyond just label and ATTR?

It turns out, the answer is right here down on your web and debug toolbar. Click the little clipboard icon to be taken to the forms part of the profiler. Now check this out, it shows the genus form and it's got a list of all of our fields, and if you click on subfamily, it gives you a lot of good information. It gives you information about the submitted data. Also, it gives you information about options that you passed to it, when you actually originally created that form. The most important thing is these view variables. This is a list of all of the variables that you can override on rendering your field.

Now most of them are really custom and you don't need to mess with, but check this out. You have the ID attribute. You have the name attribute. You have the label that you can override. Label ATTR, in case you want to put an attribute on your label elements. All kinds of really, really powerful stuff. In fact, there's actually one called disabled. Turns out that you can, instead of passing a disabled attribute, if you want to, you can pass a disabled variable, and this will in turn actually set a disabled attribute.

It does the same thing. Plus, try and setting disabled to true. Then we'll go back. Revisit our page, it's still disabled. Lesson number one is, use the profile to know what variables you have at your disposal. These variables are only going to become more and more important as we get deeper into things.

Now check this out. Under subfamily, one of the other variables that we have here is called placeholder. Right now, it's set to choose a subfamily. What this is referring to ... Let's actually, undisable the field temporarily. This refers to the option that shows up on top. It's set to choose a subfamily, because when we originally set up the field, we passed an option of placeholder, called "Choose a Subfamily." This is really interesting.

When I set up the field, there's an option called placeholder, and now I'm showing you that down here, we can pass a variable when rendering it, called placeholder. Let's set it to select a subfamily and see what happens between the placeholder option, and the placeholder option. We go back and refresh. The one that wins is actually the variable that we did in the view. I wanted to show you this because here is the really important thing. Whenever you set up a field in your form, you have a set of options you can pass to it. These aren't different than the variables that you have here. You have options in your form type, and you have view variables on your rendering field. Sometimes, they're the same. For example, there's a placeholder option, and there's a placeholder view variable.

For the most part, these are two separate ideas, so keep them separate in your head. Later, I'm going to actually show you how sometimes an option can influence a variable. For the most part, keep these ideas completely separate. Typically, options are for things like setting up how your field should function, like which table the drop down should come from. Variables usually are all about how things are rendered, like the placeholder, or the class.

Now, one more really cool thing here, is that we've been talking about these variables, well there's another way that you can get a list of all the variables for a specific field. That is to use twig's dump function. You see, when you say genusform.subfamily, that is actually an instance of a form view object. A form view object basically has nothing important on it, except that it has a public VARS property. Which is going to hold those variables. We can say DumpGenusForm.subfamily.VARS.

Scroll back, refresh. Boom, look at that. Full list, all variables that we have for this specific field. This is going to become important later for several different reasons.