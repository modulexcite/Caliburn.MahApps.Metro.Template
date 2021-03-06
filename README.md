# Caliburn.Micro and MahApps.Metro template

Template project for [Caliburn.Micro](https://github.com/Caliburn-Micro/Caliburn.Micro) WPF application using [MahApps.Metro](https://github.com/MahApps/MahApps.Metro) windows.

## What it uses

* Caliburn.Micro is the chosen MVVM framework, to bind your ViewModels to your Views. If you're not already using MVVM, use it.
* MahApps.Metro provides a quick and easy way to get a nice-looking application from the start.
* [MahApps.Metro.SimpleChildWindow](https://github.com/punker76/MahApps.Metro.SimpleChildWindow) will help you create nice-looking modal popups.
* `IPropertyChanged` notifications are implemented using [Fody.PropertyChanged](https://github.com/Fody/PropertyChanged). Just use `using PropertyChanged;` and add `[ImplementPropertyChanged]` to your ViewModels.
* NLog takes care of logging purposes; see `App.cs` for a sample usage using `Caliburn.Micro.Logging`.

## How it works

* A bootstrapper is registered in the `App.xaml` resources
* This bootstrapper then loads the `MainViewModel` through IoC and makes use of the `AppWindowManager`
* The `AppWindowManager` makes use of the `BaseWindow` or the `BaseDialogWindow`, which are using MahApps.Metro
* The `MasterViewModel` is a `Conductor`, which means it only "wires" the screens together. By default, it loads the `MainViewModel`.
