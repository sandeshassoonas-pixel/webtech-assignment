using System;

class Button
{
    public delegate void ClickHandler();
    public event ClickHandler Click;

    public void OnClick()
    {
        Console.WriteLine("Button clicked.");
        Click?.Invoke();
    }
}

class Program
{
    static void ButtonClicked()
    {
        Console.WriteLine("Event received.");
    }

    static void Main()
    {
        Button btn = new Button();

        btn.Click += ButtonClicked;

        btn.OnClick();
    }
}**
