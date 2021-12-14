<!--
A repository template for creating new examples.
-->

# MaskedInput for Blazor - How to create an input with credit card number, month/year and CVV

Here is an example of how to use MaskedInput component to show a large input with credit card number, month/year and CVV as shown below:

![alt text](https://github.com/dlvaleroso98/How-to-create-MaskedInput-with-credit-card-number-valid-month-year-CVV-and-ZIP/blob/21.2.3%2B/sample.jpg)

The main idea is to use multiple MaskedInputs for Card number, valid month/year and CVV. Then remove their borders and put them inside a div container.

# Razor

```razor
<div class="container-input">
    <div>
        <DxMaskedInput @bind-Value="@CardNumber"
                       InputCssClass="border-none"
                       Mask="\d{4} \d{4} \d{4} \d{4}" MaskMode="MaskMode.RegEx"
                       NullText="Card Number">
            <DxRegExMaskProperties PlaceholdersVisible="false"></DxRegExMaskProperties>
        </DxMaskedInput>
    </div>
    <div>
        <DxMaskedInput @bind-Value="@Date"
                       Mask="@DateTimeMaskValue"
                       InputCssClass="border-none"
                       NullText="MM/YY"
                       CssClass="width-sm">
        </DxMaskedInput>
        <DxMaskedInput @bind-Value="@CVV"
                       InputCssClass="border-none"
                       Mask="\d{3}" MaskMode="MaskMode.RegEx"
                       CssClass="width-sm"
                       NullText="CVV">
            <DxRegExMaskProperties PlaceholdersVisible="false"></DxRegExMaskProperties>
        </DxMaskedInput>
    </div>
</div>
<br />
<div class="container-input">
    <DxMaskedInput @bind-Value="@CardHolder" CssClass="w-100"
                   InputCssClass="border-none"
                   Mask="([A-Z]+ ?){1,3}" MaskMode="MaskMode.RegEx"
                   NullText="HOLDER NAME">
        <DxRegExMaskProperties PlaceholdersVisible="false"></DxRegExMaskProperties>
    </DxMaskedInput>
</div>
@code {
    DateTime? Date { get; set; } = null;
    string DateTimeMaskValue = "MM/yy";
    long? CardNumber { get; set; }
    int? CVV { get; set; }
    int? ZIP { get; set; }
}
```
# CSS

```css
    .border-none {
        border: 0 !important;
        box-shadow: none !important;
    }
    .container-input {
        display: flex;
        justify-content: space-between;
        width: 500px;
        border: 2px solid black ;
    }
        .container-input > div {
            display: flex;
        }
    .width-sm {
        width:75px;
    }
    .width-la {
        width: 250px;
    }
```

<!-- default file list -->

## Files to Look At

- [Index.razor](./CS/BlazorServerApp/Pages/Index.razor)

<!-- default file list end -->

<!--

## Documentation

- link
- link
- ...

## More Examples

- link
- link
- ...

-->
