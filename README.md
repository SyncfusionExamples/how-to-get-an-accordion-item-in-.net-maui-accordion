# how-to-get-an-accordion-item-in-.net-maui-accordion
This sample shows how to generate and access Accordion items in a .NET MAUI application using the Syncfusion `SfAccordion` control with `BindableLayout.ItemsSource`.

It follows the practical pattern shown in the Syncfusion MAUI Accordion documentation: drive the accordion from a ViewModel collection and produce one `AccordionItem` per model instance using a `BindableLayout.ItemTemplate`.

For the official documentation and additional details about .NET MAUI Accordion (SfAccordion), please refer: 
- [Getting Started with MAUI Accordion](https://help.syncfusion.com/maui/accordion/getting-started)

## Overview

This project demonstrates a minimal, data-driven approach:

- Place an `SfAccordion` in your page and set `BindableLayout.ItemsSource` to a collection exposed by the page's BindingContext.
- Define a `BindableLayout.ItemTemplate` that produces `AccordionItem` elements. Inside the template bind the header and content to the current model instance.
- Optionally use a behavior or code-behind to programmatically access `AccordionItem`s (for example, by ClassId or by traversing the `Accordion.Items` collection at runtime).

## XAML 

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

## How it works

1. BindingContext: The page sets its BindingContext to an `ItemInfoRepository` (a view model) that exposes an `Info` collection. Each element in `Info` represents one accordion item.
2. BindableLayout.ItemsSource: When `BindableLayout.ItemsSource` is assigned the `Info` collection, the `SfAccordion` uses the `ItemTemplate` to create an `AccordionItem` for each model.
3. Template bindings: Inside the `DataTemplate` you can bind header values (`Name`) and content (`Description`) directly to the current model. In this sample each `AccordionItem` receives a `ClassId` bound from the model (`ClassID`) which can make it easier to locate the generated visual element at runtime.

##### Conclusion
I hope you enjoyed learning about how to generate and access Accordion items in .NET MAUI Accordion(SfAccordion).

You can refer to our [.NET MAUI Accordion](https://www.syncfusion.com/maui-controls/maui-accordion) feature tour page to know about its other groundbreaking feature representations. You can also explore our [.NET MAUI Accordion documentation](https://help.syncfusion.com/maui/accordion/getting-started) to understand how to present and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/account/login) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/maui) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums/), [Direct-Trac](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/maui?control=sflistview). We are always happy to assist you!
