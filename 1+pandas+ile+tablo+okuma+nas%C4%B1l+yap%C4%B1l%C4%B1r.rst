
.. code:: ipython3

    import pandas as pd

.. code:: ipython3

    # URL üzerinden Chipotle siparişlerinin bir değişkene atayalım.
    siparisler = pd.read_table('http://bit.ly/chiporders')
    
    # çekmiş olduğumuz tablonun ilk 10 satırını görüntüleyelim.
    siparisler.head(10)




.. raw:: html

    <div>
    <style>
        .dataframe thead tr:only-child th {
            text-align: right;
        }
    
        .dataframe thead th {
            text-align: left;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>order_id</th>
          <th>quantity</th>
          <th>item_name</th>
          <th>choice_description</th>
          <th>item_price</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>1</td>
          <td>1</td>
          <td>Chips and Fresh Tomato Salsa</td>
          <td>NaN</td>
          <td>$2.39</td>
        </tr>
        <tr>
          <th>1</th>
          <td>1</td>
          <td>1</td>
          <td>Izze</td>
          <td>[Clementine]</td>
          <td>$3.39</td>
        </tr>
        <tr>
          <th>2</th>
          <td>1</td>
          <td>1</td>
          <td>Nantucket Nectar</td>
          <td>[Apple]</td>
          <td>$3.39</td>
        </tr>
        <tr>
          <th>3</th>
          <td>1</td>
          <td>1</td>
          <td>Chips and Tomatillo-Green Chili Salsa</td>
          <td>NaN</td>
          <td>$2.39</td>
        </tr>
        <tr>
          <th>4</th>
          <td>2</td>
          <td>2</td>
          <td>Chicken Bowl</td>
          <td>[Tomatillo-Red Chili Salsa (Hot), [Black Beans...</td>
          <td>$16.98</td>
        </tr>
        <tr>
          <th>5</th>
          <td>3</td>
          <td>1</td>
          <td>Chicken Bowl</td>
          <td>[Fresh Tomato Salsa (Mild), [Rice, Cheese, Sou...</td>
          <td>$10.98</td>
        </tr>
        <tr>
          <th>6</th>
          <td>3</td>
          <td>1</td>
          <td>Side of Chips</td>
          <td>NaN</td>
          <td>$1.69</td>
        </tr>
        <tr>
          <th>7</th>
          <td>4</td>
          <td>1</td>
          <td>Steak Burrito</td>
          <td>[Tomatillo Red Chili Salsa, [Fajita Vegetables...</td>
          <td>$11.75</td>
        </tr>
        <tr>
          <th>8</th>
          <td>4</td>
          <td>1</td>
          <td>Steak Soft Tacos</td>
          <td>[Tomatillo Green Chili Salsa, [Pinto Beans, Ch...</td>
          <td>$9.25</td>
        </tr>
        <tr>
          <th>9</th>
          <td>5</td>
          <td>1</td>
          <td>Steak Burrito</td>
          <td>[Fresh Tomato Salsa, [Rice, Black Beans, Pinto...</td>
          <td>$9.25</td>
        </tr>
      </tbody>
    </table>
    </div>



.. code:: ipython3

    # yeni veri setini URL üzerinden çekmeden önce sütun isimlerini değiştirerek aynı işlemleri tekrarlayalım.
    sutun_isimleri = ['Kullanıcı No', 'Yaş', 'Cinsiyet', 'Meslek', 'Posta Kodu']
    kullanicilar = pd.read_table('http://bit.ly/movieusers', sep='|', header=None, names=sutun_isimleri)
    kullanicilar.head(10)




.. raw:: html

    <div>
    <style>
        .dataframe thead tr:only-child th {
            text-align: right;
        }
    
        .dataframe thead th {
            text-align: left;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>Kullanıcı No</th>
          <th>Yaş</th>
          <th>Cinsiyet</th>
          <th>Meslek</th>
          <th>Posta Kodu</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>1</td>
          <td>24</td>
          <td>M</td>
          <td>technician</td>
          <td>85711</td>
        </tr>
        <tr>
          <th>1</th>
          <td>2</td>
          <td>53</td>
          <td>F</td>
          <td>other</td>
          <td>94043</td>
        </tr>
        <tr>
          <th>2</th>
          <td>3</td>
          <td>23</td>
          <td>M</td>
          <td>writer</td>
          <td>32067</td>
        </tr>
        <tr>
          <th>3</th>
          <td>4</td>
          <td>24</td>
          <td>M</td>
          <td>technician</td>
          <td>43537</td>
        </tr>
        <tr>
          <th>4</th>
          <td>5</td>
          <td>33</td>
          <td>F</td>
          <td>other</td>
          <td>15213</td>
        </tr>
        <tr>
          <th>5</th>
          <td>6</td>
          <td>42</td>
          <td>M</td>
          <td>executive</td>
          <td>98101</td>
        </tr>
        <tr>
          <th>6</th>
          <td>7</td>
          <td>57</td>
          <td>M</td>
          <td>administrator</td>
          <td>91344</td>
        </tr>
        <tr>
          <th>7</th>
          <td>8</td>
          <td>36</td>
          <td>M</td>
          <td>administrator</td>
          <td>05201</td>
        </tr>
        <tr>
          <th>8</th>
          <td>9</td>
          <td>29</td>
          <td>M</td>
          <td>student</td>
          <td>01002</td>
        </tr>
        <tr>
          <th>9</th>
          <td>10</td>
          <td>53</td>
          <td>M</td>
          <td>lawyer</td>
          <td>90703</td>
        </tr>
      </tbody>
    </table>
    </div>


