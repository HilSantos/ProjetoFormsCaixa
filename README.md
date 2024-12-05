# https://t.me/seaidear
# https://t.me/seaidear


# ProjetoFormsCaixa
UTILIZANDO VISUAL STUDIO COM WINDOWS FORMS, CRIE UM PROJETO DE FORMA QUE EXIBA INICIALMENTE EM UMA LABEL O SALDO DA CONTA DA PESSOA EM R$5.236,00. TENHA UM CAMPO QUE A PESSOA INFORMARÁ QUANTO
ELA VAI DEPOSITAR NA SUA CONTA E OUTRO CAMPO PARA INFORMAR QUANTO ELA VAI SACAR DA SUA CONTA. AO PRESSIONAR O BOTÃO, FAÇA O CÁLCULO NO DEPÓSITO DO VALOR NO SEU SALDO EM CONTA OU DO SAQUE. E AO FINAL, EXIBA QUANTO TEM EM SALDO FINAL. 
NÃO ESQUEÇA DE CRIAR O BOTÃO DE LIMPAR CAMPOS, E NÃO ESQUEÇA DE VALIDAR OS CAMPOS SE ESTÃO PREENCHIDOS OU NÃO.

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace ProjetoFormsCaixa
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

  private void btnCalcular_Click(object sender, EventArgs e)
        {
            double saldo = 5236.00;
            {
                if (double.TryParse(txtDeposito.Text, out double deposito) && double.TryParse(txtSaque.Text, out double saque))
                {
                    saldo = deposito;
                    saldo = saque;

  if (saldo < 0)
                    {
                        lblResultado.Text = "Saldo insuficiente!";
                    }
                    else
                    {
                        lblResultado.Text = "Saldo final: R$ " + saldo.ToString("F2");
                    }
                }
                else
                {
                    lblResultado.Text = "Valores inválidos. Digite apenas números.";
                }
            }
        }

private void btnLimpar_Click(object sender, EventArgs e)
        {
            txtDeposito.Text = "";
            txtSaque.Text = "";
            lblResultado.Text = "";
        }
    }
}
