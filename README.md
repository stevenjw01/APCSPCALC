# APCSPCALC

# Actual Code
```
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Aaron_Brandon_Calc
{
    public partial class Form1 : Form
    {
        Double value = 0;
        String op = "";
        bool opPress = false;

        public Form1()
        {
            InitializeComponent();
        }
        private void button_Click(object sender, EventArgs e)
        {
            //Easily get rid of the 0
            if((result.Text == "0")||(opPress))
            {
                result.Clear();
            }

            //Convert object sender into a button
            opPress = false; //set true you'll see when I declared in the front it was false
            Button b = (Button)sender;
            result.Text = result.Text + b.Text;
        }

        private void button17_Click(object sender, EventArgs e)
        {
            ///////////////
            //CLEAR ENTRY//
            ///////////////
            result.Text = "0";
        }
        private void opclick(object sender, EventArgs e)
        {
            ///////////////////
            //OPERATION CLICK//
            ///////////////////


            //Convert object sender into a button
            Button b = (Button)sender;
            op = b.Text; //set operation to a text value
            value = Double.Parse(result.Text); //you have to parse b/c it was a string
            label1.Text = value + " " + op;


        }
        private void button16_Click(object sender, EventArgs e)
        {
            /////////////////
            //EQUALS BUTTON//
            /////////////////
            result.Text = "";
            label1.Text = "";
            

            /////////////////////
            //THE ACTUAL MATH B//
            /////////////////////
            switch (op)
            {
                case "+": //ADDITION
                    result.Text = (value + Double.Parse(result.Text)).ToString();
                    break;
                case "*": //MULTIPLICATION
                    result.Text = (value * Double.Parse(result.Text)).ToString();
                    break;
                case "/": //DIVISION
                    result.Text = (value / Double.Parse(result.Text)).ToString();
                    break;
                case "-": //SUBTRACTION
                    result.Text = (value - Double.Parse(result.Text)).ToString();
                    break;
            }
            


        }

        private void button18_Click(object sender, EventArgs e)
        {
            ////////////////
            //CLEAR BUTTON//
            ////////////////

            result.Text = "0";
            value = 0;

        }
    }
}
```
