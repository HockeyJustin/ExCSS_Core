# ExCSS With Updates for .NET Core

These changes have been merged into [ExCSS](https://github.com/HockeyJustin/ExCSS_Core/issues/16). Please use the main repository 

[ExCSS](https://github.com/TylerBrinks/ExCSS) 


## Example usage (simple)

```C#
// Could read in a file here...
string css = "html{ background-color: #5a5eed; color: #FFFFFF; margin: 5px; } h2{ background-color: red }";

var stylesheet = new ExCSS.StylesheetParser().Parse(css);


// Get the info out - New way
var info = stylesheet.StyleRules.First() as ExCSS.StyleRule;
var selector = info.SelectorText;
var backgroundColor = info.Style.BackgroundColor;
var foregroundColor = info.Style.Color;
var margin = info.Style.Margin;


//// Create a new stylesheet
var newParser = new ExCSS.StylesheetParser();

ExCSS.StyleRule r = new ExCSS.StyleRule(newParser);
r.SelectorText = "h1";
r.Style.BackgroundColor = "red";

ExCSS.StyleRule r2 = new ExCSS.StyleRule(newParser);
r2.SelectorText = "h2";
r2.Style.BackgroundColor = "green";

var newstylesheet = r.ToCss() + System.Environment.NewLine + r2.ToCss();

```