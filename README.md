using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace time
{
    public partial class Form1 : Form
    {
     
        DateTime dtStart;
        DateTime dtEnd;
        TimeSpan DtTimeSpan;
        public Form1()

        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            //Get the current time in Time-In textbox
            Timein.Text = Convert.ToString(DateTime.Now);

            //Convert to datatype the value of Time-Integer of Textbox
            double timeInt = Convert.ToDouble(Timeinteger.Text);

            //Convert to data type the value of Time-In textbox
            dtStart = Convert.ToDateTime(Timein.Text);
            
            //Create DateTime variable then add to Time Int Variable
            DateTime totalTime = dtStart.AddHours(timeInt);

            //Get the Totaltime in TimeSet Text
            Timeset.Text = Convert.ToString(totalTime);
        }

        private void button2_Click(object sender, EventArgs e)
        //Calculate the total time in Time-In and Time-Out
        {
            Timeout.Text = Convert.ToString(DateTime.Now);
            dtStart = Convert.ToDateTime(Timein.Text);
            dtEnd = Convert.ToDateTime(Timeout.Text);
            DtTimeSpan = dtEnd.Subtract(dtStart);
            Totaltime.Text = Convert.ToString(DtTimeSpan);
        }
