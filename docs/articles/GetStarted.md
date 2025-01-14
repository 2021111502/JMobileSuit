# Get Started

PlasticMetal.MobileSuit is a powerful tool to quickly build a .NET Core ConsoleApp.
Now, it is migrated to Java platform, which is called JMobileSuit.

## Create your project

So firstly, you need to create a new Application in your IDE.

Then, you should add [ReFreSH.JMobileSuit](https://central.sonatype.com/artifact/io.github.hit-refresh/JMobileSuit) to
your project.

## Write the MobileSuit Client class

### Create the class

Add a Class to your project, named ***Client*** . It inherits class ***ReFreSH.JMobileSuit.ObjectModel.SuitClient*** .

### Add custom attributes to the class:

*ReFreSH.JMobileSuit.ObjectModel.Annotions..SuitInfo* with argument "Demo"

### Add the first command

Add a method called ***Hello*** to class ***Client*** . It has no parameters and return value.

The content of method can be anything you like. You can use *IO().WriteLine* and *IO().ReadLine* instead of
*System.out.println* and *Scanner::nextLine*.

### Add information and Alias for the first command

Add custom attributes to the method:

1. *ReFreSH.JMobileSuit.ObjectModel.Annotions..SuitInfo* with argument "hello command."
2. *ReFreSH.JMobileSuit.ObjectModel.Annotions..SuitAlias* with argument "H"

### Add another command

Add a method called ***Bye*** to class ***Client***. It has a string parameter, named *name*. It returns a *string*.

The content of method can be anything you like. You can use *IO().WriteLine* and *IO().ReadLine* instead of
*System.out.println* and *Scanner::nextLine*.

### Add a main method for your application

Add main method

``` java
public static void main(String[] args) throws Exception{

}
```

to the class, then add the following code to main:

``` java
new SuitHost(Client.class).Run();
```

### Check your code for Client.java

It may looks like:

``` java
import ReFreSH.JMobileSuit.ObjectModel.Annotions.SuitAlias;
import ReFreSH.JMobileSuit.ObjectModel.Annotions.SuitInfo;
import ReFreSH.JMobileSuit.ObjectModel.SuitClient;
import ReFreSH.JMobileSuit.SuitHost;

@SuitInfo("Demo")
public class Client extends SuitClient
{
    @SuitAlias("H")
    @SuitInfo("hello command")
    public void Hello(){
        IO().WriteLine("Hello! MobileSuit!");
    }

    public String Bye(String name)
    {
        IO().WriteLine("Bye!"+name);
        return "bye";
    }

    public static void main(String[] args) throws Exception
    {
        new SuitHost(Client.class).Run();
    }
}

```

## Run and test your Application

Build and run your application.

In the console, you may input:

1. **Help** to see help for MobileSuit
2. **List** or **ls** to see all available commands for current client.
3. **Hello** or **h** to run *Client.Hello()*
4. **Bye** ***name*** to run *Client.Bye(* ***name*** *)*
5. **Exit** to exit the progress

The process of build such a app is so easy that you just need one class to write.