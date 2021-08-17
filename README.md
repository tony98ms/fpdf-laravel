# Laravel package for Fpdf
[![Latest Stable Version](https://poser.pugx.org/tonystore/fpdf-laravel/v/stable?format=flat-square)](https://packagist.org/packages/tonystore/fpdf-laravel)
[![Total Downloads](https://poser.pugx.org/tonystore/fpdf-laravel/downloads?format=flat-square)](https://packagist.org/packages/tonystore/fpdf-laravel)
[![License](https://poser.pugx.org/tonystore/fpdf-laravel/license?format=flat-square)](https://packagist.org/packages/tonystore/fpdf-laravel)

This package uses [FPDF](http://www.fpdf.org/) and allows integration with [Laravel](https://laravel.com/), and is based on the [crabbly/fpdf-laravel](https://github.com/crabbly/fpdf-laravel) package, but with an updated version of [FPDF](http://www.fpdf.org/).


## INSTALLATION VIA COMPOSER

### Step 1: Composer

Run this command line in console.

```sh
composer require tonystore/fpdf-laravel
```
### Step 2: Service Provider

For your Laravel app, open `config/app.php` and, within the `providers` array, append:

```
Tonystore\Fpdf\FpdfServiceProvider::class
```

## Usage

We can resolve the FPDF class instance out of the container:

```
$pdf = app('Fpdf');

```

OR

```
$pdf = new Fpdf();

```

## Example

Create a 'Hello World' PDF document and display it in the browser:

```php
use Illuminate\Support\Facades\Storage;

//create pdf document
$pdf = new Fpdf('P', 'mm', 'A4'); //Attributes assigned to the document.
$pdf->AddPage();
$pdf->SetFont('Arial','B',16);
$pdf->Cell(40,10,'Hello World!');
$pdf->Output(); // 'I' is the default output.
exit;

```
