- 👋 Hi, I’m @HunzalaBashir
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
HunzalaBashir/HunzalaBashir is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
using System;
using System.Drawing;
using System.Windows.Forms;

namespace WindowsFormsApp
{
    public partial class MainForm : Form
    {
        public MainForm()
        {
            InitializeComponent();
        }

        private void InitializeComponent()
        {
            // Form properties
            this.Text = "Windows Forms Controls Demo";
            this.Size = new Size(800, 600);

            // MessageBox Button
            Button btnShowMessage = new Button
            {
                Text = "Show MessageBox",
                Location = new Point(50, 50)
            };
            btnShowMessage.Click += (sender, e) =>
            {
                MessageBox.Show("Hello, this is a MessageBox!", "MessageBox Demo");
            };
            this.Controls.Add(btnShowMessage);

            // Label
            Label label = new Label
            {
                Text = "This is a Label:",
                Location = new Point(50, 100),
                AutoSize = true
            };
            this.Controls.Add(label);

            // TextBox
            TextBox textBox = new TextBox
            {
                Location = new Point(150, 100),
                Width = 200
            };
            this.Controls.Add(textBox);

            // RichTextBox
            RichTextBox richTextBox = new RichTextBox
            {
                Location = new Point(50, 150),
                Width = 300,
                Height = 100
            };
            this.Controls.Add(richTextBox);

            // CheckBox
            CheckBox checkBox = new CheckBox
            {
                Text = "CheckBox",
                Location = new Point(50, 270),
                AutoSize = true
            };
            checkBox.CheckedChanged += (sender, e) =>
            {
                MessageBox.Show("CheckBox is " + (checkBox.Checked ? "Checked" : "Unchecked"));
            };
            this.Controls.Add(checkBox);

            // RadioButton
            RadioButton radioButton = new RadioButton
            {
                Text = "RadioButton",
                Location = new Point(150, 270),
                AutoSize = true
            };
            radioButton.CheckedChanged += (sender, e) =>
            {
                MessageBox.Show("RadioButton is " + (radioButton.Checked ? "Selected" : "Deselected"));
            };
            this.Controls.Add(radioButton);

            // ComboBox
            ComboBox comboBox = new ComboBox
            {
                Location = new Point(50, 320),
                Width = 200
            };
            comboBox.Items.AddRange(new string[] { "Item 1", "Item 2", "Item 3" });
            comboBox.SelectedIndexChanged += (sender, e) =>
            {
                MessageBox.Show("Selected Item: " + comboBox.SelectedItem);
            };
            this.Controls.Add(comboBox);

            // NumericUpDown
            NumericUpDown numericUpDown = new NumericUpDown
            {
                Location = new Point(50, 370),
                Width = 100,
                Minimum = 0,
                Maximum = 10
            };
            numericUpDown.ValueChanged += (sender, e) =>
            {
                MessageBox.Show("Numeric Value: " + numericUpDown.Value);
            };
            this.Controls.Add(numericUpDown);

            // DateTimePicker
            DateTimePicker dateTimePicker = new DateTimePicker
            {
                Location = new Point(50, 420),
                Width = 200
            };
            dateTimePicker.ValueChanged += (sender, e) =>
            {
                MessageBox.Show("Selected Date: " + dateTimePicker.Value.ToShortDateString());
            };
            this.Controls.Add(dateTimePicker);

            // MonthCalendar
            MonthCalendar monthCalendar = new MonthCalendar
            {
                Location = new Point(300, 370)
            };
            monthCalendar.DateChanged += (sender, e) =>
            {
                MessageBox.Show("Calendar Date Selected: " + monthCalendar.SelectionStart.ToShortDateString());
            };
            this.Controls.Add(monthCalendar);

            // PictureBox
            PictureBox pictureBox = new PictureBox
            {
                Location = new Point(500, 50),
                Size = new Size(200, 200),
                BorderStyle = BorderStyle.Fixed3D,
                SizeMode = PictureBoxSizeMode.StretchImage
            };

            try
            {
                pictureBox.Image = Image.FromFile("path_to_image.jpg"); // Replace with a valid image path
            }
            catch
            {
                MessageBox.Show("Image not found. Please check the path.");
            }

            this.Controls.Add(pictureBox);
        }
    }

    public static class Program
    {
        [STAThread]
        public static void Main()
        {
            Application.EnableVisualStyles();
            Application.SetCompatibleTextRenderingDefault(false);
            Application.Run(new MainForm());
        }
    }
}
