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

## Member Access (Data Binding Expressions)
  
It will find the first item that matches the following pattern:
1. A public method with a named prefixed by get
2. A public method with a name
3. A public field with a name
  
<img width="513" alt="image" src="https://user-images.githubusercontent.com/66931789/185508288-cf4b0064-c3b9-403e-9cb0-2916e44d2c31.png">

If there's not a matching public member you will receive an data binding error on compilation. The error message will indicate it cannot find an accessor. 

<img width="582" alt="image" src="https://user-images.githubusercontent.com/66931789/185508422-e4dd70db-6d21-4ca9-946f-1779a126a929.png">

## View Binding Strategies

- Inflate the view, then bind it. 
<img width="745" alt="image" src="https://user-images.githubusercontent.com/66931789/185509269-86404d8c-eee6-48a7-befa-0c6f461cabda.png">

- Inflate and bind at the same time
<img width="823" alt="image" src="https://user-images.githubusercontent.com/66931789/185509341-3d38ffc1-6da4-4701-9df9-c811ecc2c0fd.png">
<img width="700" alt="image" src="https://user-images.githubusercontent.com/66931789/185509375-82c24b20-0244-4855-a1d0-0c72030d3b50.png">

- Retrieve binding from an already-inflated view
**One last note here, if you created a binding previously, but don't have a reference to it you can get that reference using the DataBindingUtil.**

<img width="820" alt="image" src="https://user-images.githubusercontent.com/66931789/185509473-fc8eb557-691c-4c6e-ae60-4974ac172e84.png">


## Binding includes

<img width="586" alt="image" src="https://user-images.githubusercontent.com/66931789/185510081-4a1f09d8-550d-4166-9220-b7ca826ce812.png">

In the separated layout we declare the same variable and same name
<img width="601" alt="image" src="https://user-images.githubusercontent.com/66931789/185510198-15293d78-1bfd-4fea-9798-3ee30294c242.png">

## Binding Custom Views
Binding a custom view requires a slightly different tag than binding an activity or fragment and also requires a little more work than a simple include. 

<img width="489" alt="image" src="https://user-images.githubusercontent.com/66931789/185510743-7383cd0b-7496-4888-8614-768a2086d581.png">

<img width="520" alt="image" src="https://user-images.githubusercontent.com/66931789/185510782-2618841e-9c76-4144-9ad8-3987b2bb8cfe.png">

<img width="619" alt="image" src="https://user-images.githubusercontent.com/66931789/185510813-c70b668a-6eaf-4a0b-936f-6659c28e3a46.png">

In this case, our view will be inflated along with the activity, so we need to choose a binding method that takes an inflated view as a parameter. We can use either DataBindingUtil or DataViewbinding.

<img width="490" alt="image" src="https://user-images.githubusercontent.com/66931789/185510999-47b156ec-a90e-45c5-84db-989e9d299ded.png">

onAttachToWindow() method is called before 'onDraw()' which makes sense because you need the data before actually drawing the view. 

<img width="420" alt="image" src="https://user-images.githubusercontent.com/66931789/185511337-09bd4620-955e-47da-81a3-d09b05389d7a.png">

<img width="722" alt="image" src="https://user-images.githubusercontent.com/66931789/185511903-e9917534-2177-4e44-a01b-2a924e1212b1.png">

<img width="767" alt="image" src="https://user-images.githubusercontent.com/66931789/185511981-12903323-efaf-4481-9edb-4ece0310d176.png">

<img width="901" alt="image" src="https://user-images.githubusercontent.com/66931789/185512022-988b4e75-2754-4a99-8ec2-26151a8be732.png">


## Layout Expression Language - The power inside the "@{}"

The binding library helps you control an element's value and state. 

<img width="773" alt="image" src="https://user-images.githubusercontent.com/66931789/185512283-56670702-9e1b-4315-923e-1a11d7c76a1b.png">

The expression language is not designed for object creation, so you'll not be able to use the new keyword. If you've derived a class as variable, you will not be able to use the super keyword either to access base class members. 

<img width="686" alt="image" src="https://user-images.githubusercontent.com/66931789/185512439-8247d275-2ea8-4e10-99f1-8064307f5542.png">

<img width="888" alt="image" src="https://user-images.githubusercontent.com/66931789/185512485-e990716b-d155-4d54-be58-bf48c3369656.png">













 
  
  
  
  
  

