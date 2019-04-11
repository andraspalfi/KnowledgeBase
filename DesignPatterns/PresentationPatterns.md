Presentation Patterns
===
  
<details><summary>MVC - Model-View-Controller</summary>  
  
Controller has reference to the View and the Model, View can have a reference to the Model,

</details>

<details><summary>MVP - Model-View-Presenter</summary>  
  
Presenter has reference to the View and to the Model. The view doesn't have reference to the model or to the Controller

Passive View - MVP PV: the view no longer responsible for updating itself from the model.

Supervising Presenter - MVP SC: view uses some form of Data Binding to populate much of the information for its fields, for complex interactions then the controller steps in.

</details>

<details><summary>PM - Presentation Model</summary>

View has reference to the Presenter (presentation model), it doesn't know about the view. Presentation model fires events what are handled by the View.

</details>

<details><summary>MVVM - Model-View-ViewModel</summary>  
PM with data binding.

</details>
  
<details><summary>VIPER</summary>  
   
</details>
