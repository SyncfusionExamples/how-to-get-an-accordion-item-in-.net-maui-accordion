# how-to-get-an-accordion-item-in-.net-maui-accordion

**Repository Description**  
This repository contains a .NET MAUI sample that demonstrates how to generate and access accordion items using the Syncfusion **SfAccordion** control with `BindableLayout.ItemsSource`.

The sample follows a data‑driven MVVM pattern where each item in a ViewModel collection is rendered as an `AccordionItem`, making it easy to manage, access, and interact with accordion content at runtime.

## Project Overview
The purpose of this project is to help developers understand how to work with accordion items generated dynamically in a .NET MAUI application. It shows how to bind a collection from a ViewModel to the SfAccordion, render items using a data template, and programmatically locate accordion items using properties such as `ClassId`.

## Features
- Integration of Syncfusion .NET MAUI SfAccordion  
- Generate accordion items dynamically using `BindableLayout.ItemsSource`  
- Bind header and content values from a ViewModel  
- Access generated `AccordionItem` instances at runtime  
- Optional use of behaviors for item inspection and interaction  

## Prerequisites
Ensure the following requirements are met before running this project:
- Visual Studio 2022  
- .NET SDK compatible with .NET MAUI  

## Installation and Running the Project
1. Clone or download this repository to your local machine.
2. Open the solution in Visual Studio 2022.
3. Restore NuGet packages by rebuilding the solution.
4. Build and run the project on a supported .NET MAUI platform.

## About Sample

This sample shows how to generate and access Accordion items in a .NET MAUI application using the Syncfusion `SfAccordion` control with `BindableLayout.ItemsSource`.

**XAML**
```
<ContentPage.BindingContext>
    <local:ItemInfoRepository/>
</ContentPage.BindingContext>

<ContentPage.Content>
    <syncfusion:SfAccordion x:Name="Accordion" ExpandMode="SingleOrNone" Margin="5" BindableLayout.ItemsSource="{Binding Info}">
        <syncfusion:SfAccordion.Behaviors>
            <local:Behavior/>
        </syncfusion:SfAccordion.Behaviors>
        <BindableLayout.ItemTemplate>
            <DataTemplate>
                <syncfusion:AccordionItem x:Name="AccordionItem" ClassId="{Binding ClassID}">
                    <syncfusion:AccordionItem.Header>
                        <Grid Margin="10,0,0,0" HeightRequest="50">
                            <Label Text="{Binding Name}" VerticalOptions="Center" HorizontalOptions="StartAndExpand"/>
                        </Grid>
                    </syncfusion:AccordionItem.Header>
                    <syncfusion:AccordionItem.Content>
                        <Grid Padding="5" BackgroundColor="NavajoWhite">
                            <Label Text="{Binding Description}"/>
                        </Grid>
                    </syncfusion:AccordionItem.Content>
                </syncfusion:AccordionItem>
            </DataTemplate>
        </BindableLayout.ItemTemplate>
    </syncfusion:SfAccordion>
</ContentPage.Content>
```
### How it works
1. BindingContext: The page sets its BindingContext to an `ItemInfoRepository` (a view model) that exposes an `Info` collection. Each element in `Info` represents one accordion item.
2. BindableLayout.ItemsSource: When `BindableLayout.ItemsSource` is assigned the `Info` collection, the `SfAccordion` uses the `ItemTemplate` to create an `AccordionItem` for each model.
3. Template bindings: Inside the `DataTemplate` you can bind header values (`Name`) and content (`Description`) directly to the current model. In this sample each `AccordionItem` receives a `ClassId` bound from the model (`ClassID`) which can make it easier to locate the generated visual element at runtime.

## Usage
Run the application to see the SfAccordion populated from the `Info` collection in the ViewModel. Each element in the collection generates a corresponding `AccordionItem`. Header and content values are bound directly from the model, enabling a clean and scalable accordion structure.

## Documentation
- General Syncfusion documentation:
https://help.syncfusion.com/
- .NET MAUI Introduction:
https://help.syncfusion.com/maui/introduction/overview
- .NET MAUI Accordion Getting Started:
https://help.syncfusion.com/maui/accordion/getting-started

## Additional Resources
- Syncfusion MAUI Accordion feature tour:
https://www.syncfusion.com/maui-controls/maui-accordion

## Troubleshooting
- Verify the page BindingContext is set before initializing the accordion.
- Ensure the Info collection is populated correctly.
- Rebuild the solution if items are not rendered.
- Check output logs for binding or runtime errors.

## Conclusion
I hope you enjoyed learning about how to generate and access Accordion items in .NET MAUI Accordion(SfAccordion).

You can refer to our [.NET MAUI Accordion](https://www.syncfusion.com/maui-controls/maui-accordion) feature tour page to know about its other groundbreaking feature representations. You can also explore our [.NET MAUI Accordion documentation](https://help.syncfusion.com/maui/accordion/getting-started) to understand how to present and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/account/login) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/maui) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums/), [Direct-Trac](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/maui?control=sflistview). We are always happy to assist you!
