## Krok 0. Przygotowania - implementacja `BigRational`

W tym kroku skonfigurujesz �rodowisko projektu - utworzysz _solution_ oraz 3 projekty: typu _Class Library_, typu _Console application_ oraz typu _Unit test_.

1. Utw�rz projekt o nazwie `RationalLib` typu _Class Library_ oraz solution o nazwie `RationalType`.

    > W ramach Twojego _solution_ b�dziesz korzysta� z wielu projekt�w - m.in. projektu testuj�cego (_Unit Tests_) czy projektu z aplikacj� pr�bn�. Zatem powiniene� mie� _solution_ z mo�liwo�ci� utworzenia wielu projekt�w.

2. Dodaj do _solution_ projekt typu _Unit Tests_. Nadaj mu nazw� `RationalUnitTests`. W klasach tego projektu tworzy� b�dziesz kod test�w jednostkowych dla projektu `RationalLib`, za� uruchamia� je w _Test Explorer_.
   > Wykorzystujemy domy�lne �rodowisko test�w jednostkowych Microsoft MSTest v2.
   > Dla �rodowiska wybierz .NET6 lub wy�szy.

   Dodaj referencj� do projektu `RationalLib`.

3. W _solution_ utw�rz jeszcze jeden projekt typu _Console application_
   o nazwie `RationalConsoleAppDemo`. (Wybierz .NET6 lub wy�szy). Uczy� ten projekt aktywnym.

   W projekcie tym b�dziesz zapisywa� proste fragmenty kodu weryfikuj�cego niekt�re z funkcjonalno�ci projektowanej klasy.

   Dodaj referencj� do projektu `RationalLib` oraz wpisz w wygenerowanym `Program.cs`:

   ````csharp
   using RationalLib;
   using static System.Console;
   ````

    > Dyrektywa `using static` pozwala na odwo�ania bezpo�rednie do sk�adnik�w
    > wskazanego typu. W naszym przypadku zamiast pisa� `Console.WriteLine("abc")`
    > b�dziemy mogli napisa� `WriteLine("abc")`.

    > Zwr�� uwag�, w jakiej przestrzeni nazw zdefininiowana b�dzie klasa `BigRational` (domy�lnie nazwa projektu - czyli `RationalLib`).

   Sprawd� poprawno�� konfiguracji, uruchamiaj�c program (dopisuj�c w `Main()` lini� `WriteLine("Hello")` (dzi�ki `using static System.Console;` mo�esz w takiej skr�tej postaci wyprowadza� napisy na konsol�).

---

* Plik: `RationalLib.csproj`

   ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <TargetFramework>net6.0</TargetFramework>
        <ImplicitUsings>enable</ImplicitUsings>
        <Nullable>enable</Nullable>
      </PropertyGroup>

    </Project>
   ```

* Plik: `RationalUnitTests.csproj`

   ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <TargetFramework>net6.0</TargetFramework>
        <Nullable>enable</Nullable>

        <IsPackable>false</IsPackable>
      </PropertyGroup>

      <ItemGroup>
        <PackageReference Include="Microsoft.NET.Test.Sdk" Version="16.11.0" />
        <PackageReference Include="MSTest.TestAdapter" Version="2.2.7" />
        <PackageReference Include="MSTest.TestFramework" Version="2.2.7" />
        <PackageReference Include="coverlet.collector" Version="3.1.0" />
      </ItemGroup>

      <ItemGroup>
        <ProjectReference Include="..\RationalLib\RationalLib.csproj" />
      </ItemGroup>

    </Project>
   ```

* Plik: `RationalConsoleApp.csproj`

   ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>Exe</OutputType>
        <TargetFramework>net6.0</TargetFramework>
        <ImplicitUsings>enable</ImplicitUsings>
        <Nullable>enable</Nullable>
      </PropertyGroup>

      <ItemGroup>
        <ProjectReference Include="..\RationalLib\RationalLib.csproj" />
      </ItemGroup>

    </Project>
   ```

---

[Pocz�tek](README.md) | [Krok nast�pny](step01.md)