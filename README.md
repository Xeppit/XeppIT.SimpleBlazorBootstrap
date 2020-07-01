# XeppIT.SimpleBlazorBootstrap
A Set of Blazor components using Bootstrap.

```
<SBBInput Id="name" Label="Raaaa" Placeholder="" CustomCss="" @bind-value="value" ValidationRule="@InputValidationRule" ></SBBInput>
```

```
@code {

    private string value = "";

    string InputValidationRule(string input)
    {
        if (input.Contains("@"))
        {
            return "Input cannot contain @";
        }

        return "";
    }
}
```
