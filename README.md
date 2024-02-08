using System;
using System.Windows.Forms;                                                            

class Program                TextBox textBox = new TextBox();
                             textBox.Location = new System.Drawing.Point(10, 10);
                             form.Controls.Add(textBox);
{
    [STAThread]
    static void Main()
    {
        Form form = new Form();                 
        form.Text = "Знайти добуток цифр";
        Button button = new Button();
        button.Text = "Знайти добуток цифр";
        button.Location = new System.Drawing.Point(10, 40);
        button.Click += (sender, e) =>
        {             try
            {
                int x = int.Parse(textBox.Text);

                if (x >= 1000 && x <= 9999)
                {
                    int product = 1;
                    while (x > 0)
                    {
                        int digit = x % 10;
                        product *= digit;
                        x /= 10;
                    }

                    MessageBox.Show($"Добуток цифр: {product}");
                }
                else
                {
                    MessageBox.Show("Введіть чотиризначне число.");
                }
            }
            catch (FormatException)
            {
                MessageBox.Show("Невірний формат числа!");
            }
        };
        form.Controls.Add(button);

        Application.Run(form);
    }
}
