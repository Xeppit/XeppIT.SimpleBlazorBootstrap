# XeppIT.SimpleBlazorBootstrap
A Set of Blazor components using Bootstrap.

## Input Field

```html
<SBBInput Id="name" Label="Raaaa" Placeholder="" CustomCss="" @bind-value="value" ValidationRule="@InputValidationRule" ></SBBInput>
```

```csharp
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
## Select Field

```html
<XSelect Id="id2" Label="Raaaa" Placeholder=""  @bind-ListSelectedValue="@SelectedValue" Data="@list" TItem=Model ValidationRule="@SelectValidationRule" />
```

```csharp
@code {

    private Model SelectedValue { get; set; } = new Model();

    List<Model> list;

    protected override void OnInitialized()
    {
        list = new List<Model>()
        {
            new Model() { a = Guid.NewGuid().ToString(), b = Guid.NewGuid().ToString(), c = Guid.NewGuid().ToString() },
            new Model() { a = Guid.NewGuid().ToString(), b = Guid.NewGuid().ToString(), c = Guid.NewGuid().ToString() },
            new Model() { a = Guid.NewGuid().ToString(), b = Guid.NewGuid().ToString(), c = Guid.NewGuid().ToString() }
        };
    }
    
    string SelectValidationRule(Model input)
    {
        if (input == null)
        {
            return "Please select a value.";
        }

        return "";
    }

    public class Model
    {
        public string a { get; set; }
        public string b { get; set; }
        public string c { get; set; }

        public override string ToString()
        {
            return a;
        }
    }
}
```
