# Puzzle #75 - Instant InputText

Carl and Jeff want to know how to bind an `<InputText>` element in an `<EditForm>` that updates on every keystroke

YouTube Video: https://youtu.be/

Blazor Puzzle Home Page: https://blazorpuzzle.com

## The Challenge

This is a .NET 9 Blazor Web App with Global Server interactivity.

We have an `<EditForm>` to edit a model with two `<InputText>` elements, one of which we want the binding to update on every keystroke.

With a standard `<input>` control we ca do this with the syntax `@bind:event="oninput"` but that doesn't work on an `<InputText>`. How can we achieve this?