# Translation_website
pip install translate
from tkinter import *
from translate import Translator
#From tkinter import *: The easiest and most effective way to develop GUI applications is using tkinter. * means importing everything from tkinter.
#From translate import Translator: This package helps to translate major languages.
Screen = Tk()
Screen.title("Language Translator with GUI by- TechVidvan")
 
InputLanguageChoice = StringVar()
TranslateLanguageChoice = StringVar()
#InputLanguageChoice is a variable that stores the language of the text that is being translated.

#TranslateLanguageChoice is a variable that stores the language in which the text is to be translated.

#Tk(): Root window is created with the help of Tk() class.
#title(): It is used to display the title on the top of the root window.
LanguageChoices = {'Hindi','English','French','German','Spanish'}
InputLanguageChoice.set('English')
TranslateLanguageChoice.set('Hindi')
#Code Explanation:
#LanguageChoices is a tuple that stores five languages from which input language and translated language can be chosen.

#set(): It helps to set the value of the variable. For instance: value of InputLanguageChoice is set as English initially which can be changed afterwards and selected from the tuple.

def Translate():
    translator = Translator(from_lang= InputLanguageChoice.get(),to_lang=TranslateLanguageChoice.get())
    Translation = translator.translate(TextVar.get())
    OutputVar.set(Translation)

#This function is created to translate the text. OutputVar is a variable that stores the translated text. TextVar is a variable that contains the text that is to be translated.

#Translator(): It helps to translate the text.
#from_lang : It is the language of the text that is being translated.
#to_lang: It is the language of the text in which the text is to be translated.
#get(): Value of the item is returned with the help of this method.    

#choice for input language
InputLanguageChoiceMenu = OptionMenu(Screen,InputLanguageChoice,*LanguageChoices)
Label(Screen,text="Choose a Language").grid(row=0,column=1)
InputLanguageChoiceMenu.grid(row=1,column=1)
 
#choice in which the language is to be translated
NewLanguageChoiceMenu = OptionMenu(Screen,TranslateLanguageChoice,*LanguageChoices)
Label(Screen,text="Translated Language").grid(row=0,column=2)
NewLanguageChoiceMenu.grid(row=1,column=2)
Code Explanation:

#InputLanguageChoiceMenu provides a choice of input languages. NewLanguageChoiceMenu provides a choice of languages in which translation of text is possible.

#OptionMenu(): It provides the options that are available to the user.
#Label(): This widget helps to implement display boxes where the text can be placed.
#grid(): Widgets are arranged on the screen with the help of grid.

Label(Screen,text="Enter Text").grid(row=2,column =0)
TextVar = StringVar()
TextBox = Entry(Screen,textvariable=TextVar).grid(row=2,column = 1)
 
Label(Screen,text="Output Text").grid(row=2,column =2)
OutputVar = StringVar()
TextBox = Entry(Screen,textvariable=OutputVar).grid(row=2,column = 3)
 
#Button for calling function
B = Button(Screen,text="Translate",command=Translate, relief = GROOVE).grid(row=3,column=1,columnspan = 3)
 
mainloop()

#Code Explanation:Entry(): This widget helps to enter or display a single line text on the screen.
#Button(): This widget creates a button.
#relief: It helps to provide 3-D effects around the outside of the widget.
#mainloop(): It helps to run the tkinter event loop.

#Summary
#We have successfully developed python language translator project with translate and tkinter. This is an interesting python project for beginners, based on requirements you can add more functionalities.


