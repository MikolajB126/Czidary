<Window x:Class="SzyfrCezaraDesktop.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Szyfrowanie. Wykonane przez 123456" Height="450" Width="600"
        Background="#5F9EA0">
    <Grid Margin="20">
        <TextBlock Text="Podaj wartość klucza" Foreground="#FAEBD7"
                   FontSize="16" Margin="10,10,0,0" HorizontalAlignment="Left"
                   VerticalAlignment="Top"/>
        <TextBox x:Name="pole_klucz" Width="100" Height="25"
                 Margin="180,10,10,0" VerticalAlignment="Top"/>
        <TextBlock Text="Podaj tekst" Foreground="#FAEBD7"
                   FontSize="16" Margin="10,50,0,0" HorizontalAlignment="Left"
                   VerticalAlignment="Top"/>
        <TextBox x:Name="pole_tekst_wej" AcceptsReturn="True" TextWrapping="Wrap"
                 Margin="10,80,10,0" VerticalAlignment="Top" Height="150"/>
        <Button x:Name="przycisk_szyfruj" Content="Zaszyfruj"
                Background="#ADD8E6" Width="120" Height="35"
                Margin="10,240,0,0" VerticalAlignment="Top"
                Click="przycisk_szyfruj_Click"/>
        <TextBlock Text="Tekst zaszyfrowany" Foreground="#FAEBD7"
                   FontSize="16" Margin="10,290,0,0" HorizontalAlignment="Left"
                   VerticalAlignment="Top"/>
        <Border BorderBrush="#FAEBD7" BorderThickness="2" CornerRadius="10"
                Margin="10,320,10,10">
            <TextBox x:Name="pole_wynik" Background="Transparent"
                     Foreground="#F0F8FF" IsReadOnly="True"
                     BorderThickness="0" FontSize="14"
                     TextWrapping="Wrap"/>
        </Border>
    </Grid>
</Window>
