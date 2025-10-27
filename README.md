<Window x:Class="SzyfrCezaraDesktop.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Szyfrowanie. Wykonane przez 123456" Height="450" Width="800"
        Background="#5F9EA0">
    <Grid Margin="20">
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="2*" />
            <ColumnDefinition Width="2*" />
            <ColumnDefinition Width="1.5*" />
        </Grid.ColumnDefinitions>

        <StackPanel Grid.Column="0">
            <TextBlock Text="Podaj wartość klucza" Foreground="#FAEBD7" FontSize="16" Margin="0,0,0,10"/>
            <TextBox x:Name="pole_klucz" Width="120" Height="30" Margin="0,0,0,20"/>
            <TextBlock Text="Podaj tekst" Foreground="#FAEBD7" FontSize="16" Margin="0,0,0,10"/>
            <TextBox x:Name="pole_tekst_wej" AcceptsReturn="True" TextWrapping="Wrap" Height="180" Margin="0,0,0,20"/>
            <Button x:Name="przycisk_szyfruj" Content="Zaszyfruj" Width="150" Height="40" Background="#ADD8E6" Click="przycisk_szyfruj_Click"/>
        </StackPanel>

        <StackPanel Grid.Column="1">
            <TextBlock Text="Tekst zaszyfrowany" Foreground="#FAEBD7" FontSize="16" Margin="0,0,0,10"/>
            <Border BorderBrush="#FAEBD7" BorderThickness="2" CornerRadius="10">
                <TextBox x:Name="pole_wynik" Background="Transparent" Foreground="#F0F8FF" IsReadOnly="True" BorderThickness="0" FontSize="14" TextWrapping="Wrap" Height="250"/>
            </Border>
        </StackPanel>

        <StackPanel Grid.Column="2">
            <Button x:Name="przycisk_zapisz_szyfr" Content="Zapisz szyfr" Width="150" Height="40" Background="#ADD8E6" Margin="0,0,0,15" Click="przycisk_zapisz_szyfr_Click"/>
            <Button x:Name="przycisk_zapisz_plik" Content="Zapisz w pliku" Width="150" Height="40" Background="#ADD8E6" Click="przycisk_zapisz_plik_Click"/>
        </StackPanel>
    </Grid>
</Window>
