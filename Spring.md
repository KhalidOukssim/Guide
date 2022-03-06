#                                                SPRING

##  A - Spring MVC 

### 1-Data Binding

```java
@Controller //determine the name of controller class
@requestMapping("/route")
public String hello(Model model){
    ClassName obj= new ClassName();
    model.addAttributr("the one who we will get",obj);
    return "jsp-page-name";
}
// 2)ModelAttribute
@RequestMapping("/processForm")
	public String processForm(@ModelAttribute("student") Student theStudent) {
		
		// log the input data
		System.out.println("theStudent: " + theStudent.getFirstName()
							+ " " + theStudent.getLastName());
		
		return "student-confirmation";
	}
```

### 2 - Forms

```jsp

	<form:form action="destination" modelAttribute="student">
		First name: <form:input path="firstName" />
		<br><br>
		Last name: <form:input path="lastName" />
		<br><br>
		Country:<form:select path="country">
		<form:options items="${student.getItems}"/>
		</form:select>
		<br><br>
        <form:radiobuttons path="field in class" value=""/>
		<input type="submit" value="Submit" />
	</form:form>
```

### 3-validation : basics

```java
//controller
@RequestMapping("/processForm")
	public String processForm(@Valid @ModelAttribute("student") Student theStudent,BindingResult br) {
		if(br.hasErrors()) {
			return "student-form";
		}
		return "student-confirmation";
	}
//class
	@NotNull(message="is required")
	@Size(min=1, message="is required")
	private String lastName; 
    @NotNull(message="is required")
    @Max(value=20,message="")
    @Min(value=0,message="")
    private Integer note;//because it will show an error if it is an int java.Lang
    @Pattern(regexp="^[a-zA-Z0-9]{5}",message="only 5 chars/digits")//validation rule
    private String cin;
//jsp
Last name(*): <form:input path="lastName" />
<form:errors path="lastName" cssClass="error"/>
```

```java
@InitBinder //transform the whitespace to null
	public void initBinder(WebDataBinder dataBinder) {
	StringTrimmerEditor stringTrimmerEditor = new StringTrimmerEditor(true);
	dataBinder.registerCustomEditor(String.class, stringTrimmerEditor);
	}
```

#### messages.properties

when the user enter a text in pplace of int in note field ==>error

So we use message.properties

```properties
typeMismatch.student.note=invalid Note
```

in xml file

```xml
<bean id="messageSource">
    class="org.*********************"
    <property name="basenames" value="path in src"/> 
</bean>
```

### 04 - validation : Create your Own Annotation  //Later