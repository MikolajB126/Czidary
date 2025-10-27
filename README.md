using Microsoft.Win32;
using System;
using System.IO;
using System.Text;
using System.Windows;

namespace SzyfrCezaraDesktop
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private void przycisk_szyfruj_Click(object sender, RoutedEventArgs e)
        {
            if (!int.TryParse(pole_klucz.Text, out int klucz))
            {
                MessageBox.Show("Podaj poprawny klucz (liczba).");
                return;
            }

            string tekst = pole_tekst_wej.Text;
            if (string.IsNullOrWhiteSpace(tekst))
            {
                MessageBox.Show("Pole tekstu nie może być puste.");
                return;
            }

            pole_wynik.Text = SzyfrujCezarem(tekst, klucz);
        }

        private string SzyfrujCezarem(string tekst, int klucz)
        {
            StringBuilder wynik = new StringBuilder();
            foreach (char znak in tekst)
            {
                if (char.IsLetter(znak))
                {
                    char offset = char.IsUpper(znak) ? 'A' : 'a';
                    char nowy = (char)(((znak + klucz - offset) % 26 + 26) % 26 + offset);
                    wynik.Append(nowy);
                }
                else
                {
                    wynik.Append(znak);
                }
            }
            return wynik.ToString();
        }

        private void przycisk_zapisz_plik_Click(object sender, RoutedEventArgs e)
        {
            if (string.IsNullOrWhiteSpace(pole_wynik.Text))
            {
                MessageBox.Show("Brak szyfru do zapisania.");
                return;
            }

            SaveFileDialog dialog = new SaveFileDialog();
            dialog.Filter = "Plik tekstowy (*.txt)|*.txt";
            dialog.FileName = "szyfr_cezara.txt";

            if (dialog.ShowDialog() == true)
            {
                string zapis = "Tekst: " + pole_tekst_wej.Text + "\nKlucz: " + pole_klucz.Text + "\nSzyfr: " + pole_wynik.Text;
                File.WriteAllText(dialog.FileName, zapis);
                MessageBox.Show("Zapisano pomyślnie.");
            }
        }
    }
}
