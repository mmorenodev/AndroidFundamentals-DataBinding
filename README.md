# AndroidFundamentals-DataBinding
Learning about Data Binding on Pluralsight.


Data Binding Library Process

1. Create a binding from a layout
2. Retrieve the data
3. Bind the data to the view


This is possible because of code generation.

## Data Binding Compilaiton Process

<img width="597" alt="image" src="https://user-images.githubusercontent.com/66931789/185506693-dfaa75e3-2a19-4b93-9ef8-c73c52a26aa7.png">


## Terms 
Layout - XML file descriptioin
View - Java file subclassing an activity, fragment, or view
Binding class - **A Java file generated using code generation**
Code Generation - Compile time process to create code
Gradle Plugin - Assists in custom compilation

We need to use an Android Studio version that SUPPORTS THE USE OF DATA BINDING LIBRARY. 

<img width="566" alt="image" src="https://user-images.githubusercontent.com/66931789/185507012-7e8deaf6-547d-4007-8508-d524471a193b.png">

# Simple Data Binding

## Prepariing an XML to use DataBinding
1. Surround all the view hierarchy defined in XML with the tag <layout>
2. Inside this new XML you can have a section called <data> where you declare your variables

  <img width="595" alt="image" src="https://user-images.githubusercontent.com/66931789/185508037-452db757-6986-471e-ac70-5ec6f6bdba0b.png">

  
  

