# Puzzle #75 - Instant InputText

Carl and Jeff want to know how to bind an `<InputText>` element in an `<EditForm>` that updates on every keystroke

YouTube Video: https://youtu.be/

Blazor Puzzle Home Page: https://blazorpuzzle.com

## The Challenge

This is a .NET 9 Blazor Web App with Global Server interactivity.

We have an `<EditForm>` to edit a model with two `<InputText>` elements, one of which we want the binding to update on every keystroke.

With a standard `<input>` control we ca do this with the syntax `@bind:event="oninput"` but that doesn't work on an `<InputText>`. How can we achieve this?

## The Solution

One solution is to subclass `<InputText>` and add the required markup to handle `oninput`:

*InstantInputText.razor*:

```html
@inherits Microsoft.AspNetCore.Components.Forms.InputText
<input @attributes="@AdditionalAttributes" class="@CssClass"
          @bind="@CurrentValueAsString" @bind:event="oninput" />
```

Now we just replace the `<InputText>` in the form with an `<InstantInputText>` and remove the `oninput` event binding:

```html
<InstantInputText @bind-Value="person.Email" placeholder="Email" />
```

Boom!