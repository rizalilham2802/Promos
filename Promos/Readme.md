# Fungsionalitas

- User dapat memilih makanan yang akan di pesan
- User dapat menghapus makanan yang sudah di pesan
- User dapat melihat tampilan makanan yang di pesan

# How does it works?

Apabila user ingin melihat daftar makanan maka user harus menakan tombol + untuk mentrigger list item agar muncul, seperti pada source code dibawah

``` java
private void onButtonAddItemClicked(object sender, RoutedEventArgs e)
        {
            Penawaran penawaranWindow = new Penawaran();
            penawaranWindow.SetOnItemSelectedListener(this);
            penawaranWindow.Show();
        }
```

untuk melakukan penghapusan item yang telah diambil dilakukan pada method `removeItem` di `KeranjangBelanja.cs`

``` java
public void removeItem(Item item)
        {
            this.itemBelanja.Remove(item);
            this.callback.removeItemSucceed();
            calculateSubTotal();
        }
```

source code untuk melakukan proses perhitungan makanan yang telah di pesan
``` java
 public void updateTotal(double subtotal)
        {
            double total = subtotal + deliveryFee - promo;
            this.balance = this.balance - total;
            this.paymentCallback.onPriceUpdated(subtotal,  total, balance);
        }
```



# Tools

- Visual Studio 2017
- C# Language
