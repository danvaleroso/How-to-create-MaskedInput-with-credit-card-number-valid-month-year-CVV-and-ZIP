<!--
A repository template for creating new examples.
-->

# MaskedInput for Blazor - How to create MaskedInput with credit card number, valid month/year, CVV and ZIP

Here is an example of how to use MaskedInput component to show a large input with credit card number, valid month/year, CVV and ZIP as shown below.

![alt text](https://github.com/dlvaleroso98/How-to-create-MaskedInput-with-credit-card-number-valid-month-year-CVV-and-ZIP/blob/21.2.3%2B/Clipboard-File-1.png)

The main idea is to use multiple MaskedInputs for Card number, valid month/year, CVV and ZIP. Then remove their borders and put them inside a div container.

# Razor

```razor
<div class="inputContainer" >
    <div>
        <DxMaskedInput @bind-Value="@CardNumber"
                       InputCssClass="no-border"
                       Mask="0000 0000 0000 0000"
                       NullText="Card Number">
        </DxMaskedInput>
    </div>
    <div>
        <DxMaskedInput @bind-Value="@Date"
                       Mask="@DateTimeMaskValue"
                       InputCssClass="no-border"
                       NullText="MM/YY"
                       CssClass="widthSm">
        </DxMaskedInput>
        <DxMaskedInput @bind-Value="@CVC"
                       InputCssClass="no-border"
                       Mask="000" 
                       CssClass="widthSm"
                       NullText="CVC">
        </DxMaskedInput>
        <DxMaskedInput @bind-Value="@ZIP"
                       InputCssClass="no-border"
                       Mask="00000" CssClass="widthSm"
                       NullText="ZIP">
        </DxMaskedInput>
    </div>
</div>

@code {
    DateTime? Date { get; set; } = null;
    string DateTimeMaskValue = "MM/yy";
    int? CardNumber { get; set; }
    int? CVC { get; set; }
    int? ZIP { get; set; }
}
```
# CSS

```css
.no-border {
    border: 0 !important;
    box-shadow: none !important; 
}
.inputContainer {
    display: flex;
    justify-content: space-between;
    width: 500px;
    border: 2px solid black ;
}
    .inputContainer > div {
        display: flex;
    }
.widthSm {
    width:75px;
}
```

<!-- default file list -->

## Files to Look At

- link.cs (VB: link.vb)
- link.js
- ...

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
