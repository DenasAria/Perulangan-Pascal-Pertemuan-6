## Nama            : Denas Aria Pamungkas
## NIM             : 312010089
## Kelas           : TI.20.RPL.1
## Mata Kuliah     : Pemograman Visual
## Dosen Pengampu  : Agung Nugroho, S.Kom., M.Kom.

## Latihan Pertemuan 6
# Program Menghitung Gaji Karyawan

Menu Tampilan Awal Pada Program</br>

![Tampilan Awal](https://github.com/DenasAria/alquran-with-flutter--master/assets/101621068/767305c0-308c-4a73-b480-1c505443a34b)

Menghitung Gaji Bersih Direktur Tetap</br>

![Direktur Tetap](https://github.com/DenasAria/alquran-with-flutter--master/assets/101621068/94f99a15-fe79-4fc9-8703-23487eb0c9e0)

Menghitung Gaji Bersih Direktur Honorer</br>

![Direktur Honorer](https://github.com/DenasAria/alquran-with-flutter--master/assets/101621068/18f6884c-46f5-4d56-8bf9-b10a6c521744)

Menghitung Gaji Bersih Manager Tetap</br>

![Manager Tetap](https://github.com/DenasAria/alquran-with-flutter--master/assets/101621068/e2e0b6bd-1e28-4593-b320-18d002cbfe7f)

Menghitung Gaji Bersih Manager Honorer</br>

![Manager Honorer](https://github.com/DenasAria/alquran-with-flutter--master/assets/101621068/53c2eee3-5dec-4cd3-b24c-df944e30bd25)

Menghitung Gaji Bersih Karyawan Tetap</br>

![Karyawan Tetap](https://github.com/DenasAria/alquran-with-flutter--master/assets/101621068/95ec8457-fc76-430d-a2a9-9721721b744e)

Menghitung Gaji Bersih Karyawan Honorer</br>

![Karyawan Honorer](https://github.com/DenasAria/alquran-with-flutter--master/assets/101621068/da1f19cb-6055-4d8c-a2c8-7b98a72a73e2)

- Source Code Menghitung Gaji Bersih</br>

```pascal

procedure TForm1.btnHitungClick(Sender: TObject);
var
  GajiPokok, TotalGaji, GajiBersih: Double;
  StatusTunjangan: Double;


begin
  GajiPokok := StrToFloat(edtGapok.Text);
  StatusTunjangan := StrToFloat(edtTunjangan.Text);

  TotalGaji := GajiPokok + StatusTunjangan;

  GajiBersih := TotalGaji;

  edtTotalGaji.Text := FormatFloat('#,##0.00', TotalGaji);

end;              

```

<li>Source code Gaji Pokok Otomatis Sesuai Dengan Jabatan</li></br>

```pascal

procedure TForm1.cbJabatanChange(Sender: TObject);
var
  Jabatan: string;
  GajiPokok: Double;

begin
  Jabatan := cbJabatan.Items[cbJabatan.ItemIndex];

  case Jabatan of
    'Direktur': GajiPokok := 5000000;
    'Manager': GajiPokok := 3000000;
    'Karyawan': GajiPokok := 1000000;
  else
    GajiPokok := 0; // Nilai default jika jabatan tidak ada
  end;

  edtGapok.Text := FloatToStr(GajiPokok);
end;

end.     


```

<li>Source code Status Tunjangan Otomatis Sesuai Dengan Status</li></br>

```pascal

procedure TForm1.rbHonorerChange(Sender: TObject);
begin
  if rbHonorer.Checked then
    edtTunjangan.Caption := '500000';

end;

procedure TForm1.rbTetapChange(Sender: TObject);
begin
  if rbTetap.Checked then
    edtTunjangan.Caption := '1500000';
end; 


```

<li>Full Source Code Programnya</li></br>

```pascal

unit Unit1;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils, Forms, Controls, Graphics, Dialogs, StdCtrls, ExtCtrls;

type

  { TForm1 }

  TForm1 = class(TForm)
    btnHitung: TButton;
    btnIsiData: TButton;
    btnClose: TButton;
    cbJabatan: TComboBox;
    edtTotalGaji: TEdit;
    edtTunjangan: TEdit;
    edtGapok: TEdit;
    edtNama: TEdit;
    Label1: TLabel;
    Label2: TLabel;
    Label3: TLabel;
    Label4: TLabel;
    Label5: TLabel;
    rbHonorer: TRadioButton;
    rbTetap: TRadioButton;
    rgStatus: TRadioGroup;
    procedure btnHitungClick(Sender: TObject);
    procedure cbJabatanChange(Sender: TObject);
    procedure rbHonorerChange(Sender: TObject);
    procedure rbTetapChange(Sender: TObject);
    procedure rgStatusClick(Sender: TObject);
  private

  public

  end;

var
  Form1: TForm1;

implementation

{$R *.lfm}

{ TForm1 }

procedure TForm1.rbHonorerChange(Sender: TObject);
begin
  if rbHonorer.Checked then
    edtTunjangan.Caption := '500000';

end;

procedure TForm1.rbTetapChange(Sender: TObject);
begin
  if rbTetap.Checked then
    edtTunjangan.Caption := '1500000';
end;

procedure TForm1.rgStatusClick(Sender: TObject);
begin


end;

procedure TForm1.btnHitungClick(Sender: TObject);
var
  GajiPokok, TotalGaji, GajiBersih: Double;
  StatusTunjangan: Double;


begin
  GajiPokok := StrToFloat(edtGapok.Text);
  StatusTunjangan := StrToFloat(edtTunjangan.Text);

  TotalGaji := GajiPokok + StatusTunjangan;

  GajiBersih := TotalGaji;

  edtTotalGaji.Text := FormatFloat('#,##0.00', TotalGaji);

end;

procedure TForm1.cbJabatanChange(Sender: TObject);
var
  Jabatan: string;
  GajiPokok: Double;

begin
  Jabatan := cbJabatan.Items[cbJabatan.ItemIndex];

  case Jabatan of
    'Direktur': GajiPokok := 5000000;
    'Manager': GajiPokok := 3000000;
    'Karyawan': GajiPokok := 1000000;
  else
    GajiPokok := 0; // Nilai default jika jabatan tidak ada
  end;

  edtGapok.Text := FloatToStr(GajiPokok);
end;

end.

end;

end.

end;

end;

end.


```

