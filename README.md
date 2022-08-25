# C-TOTAL-TIME-CODE
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
        string strStarttime;
        string strEndtimes;
        DateTime dtStart;
        DateTime dtEnd;
        TimeSpan DtTimeSpan;
        public Form1()

        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            Timein.Text = Convert.ToString(DateTime.Now);
        }

        private void button2_Click(object sender, EventArgs e)
        {
            Timeout.Text = Convert.ToString(DateTime.Now);
            strStarttime = Timein.Text;
            strEndtimes = Timeout.Text;

          

            dtStart = Convert.ToDateTime(strStarttime);
            dtEnd = Convert.ToDateTime(strEndtimes);
            DtTimeSpan = dtEnd.Subtract(dtStart);
            Totaltime.Text = Convert.ToString(DtTimeSpan);
        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }
    }
}
