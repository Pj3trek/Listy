import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('data.csv')

# 1. Histogram liczby kilometrów przejechanych przez pojazd
mean_km_driven = data['Kilometers_Driven'].mean()
print("Średnia liczba kilometrów przejechanych przez pojazd:", mean_km_driven)

# 2. Analiza rodzaju paliwa
fuel_type_counts = data['Fuel_Type'].value_counts()
print("\nAnaliza rodzaju paliwa:")
print(fuel_type_counts)

# 3. Analiza liczby miejsc w pojazdach
seats_counts = data['Seats'].value_counts()
print("\nAnaliza liczby miejsc w pojazdach:")
print(seats_counts)

# 5. Zależność ceny od roku produkcji
mean_price_per_year = data.groupby('Year')['Price'].mean()
print("\nZależność średniej ceny od roku produkcji:")
print(mean_price_per_year)

# 6. Analiza średniej ceny w zależności od rodzaju paliwa
mean_price_per_fuel_type = data.groupby('Fuel_Type')['Price'].mean()
print("\nAnaliza średniej ceny w zależności od rodzaju paliwa:")
print(mean_price_per_fuel_type)

# 7. Analiza średniej ceny w zależności od rodzaju skrzyni biegów
mean_price_per_transmission = data.groupby('Transmission')['Price'].mean()
print("\nAnaliza średniej ceny w zależności od rodzaju skrzyni biegów:")
print(mean_price_per_transmission)


# 1. Obliczenie średniej liczby kilometrów przejechanych przez pojazd
average_kilometers_driven = df['Kilometers_Driven'].mean()

# 2. Znalezienie największej liczby kilometrów
max_kilometers_driven = df['Kilometers_Driven'].max()

# 3. Obliczenie najczęściej występującego rodzaju paliwa
most_common_fuel_type = df['Fuel_Type'].mode()[0]

# 4. Obliczenie najczęściej występującego rodzaju skrzyni biegów
most_common_transmission = df['Transmission'].mode()[0]

# 5. Obliczenie najczęściej spotykanego typu właściciela
most_common_owner_type = df['Owner_Type'].mode()[0]

# Wyświetlenie wyników
print("Średnia liczba kilometrów przejechanych przez pojazd: {:.2f}".format(average_kilometers_driven))
print("Największa liczba kilometrów przejechanych przez pojazd:", max_kilometers_driven)
print("Najczęściej występujący rodzaj paliwa:", most_common_fuel_type)
print("Najczęściej występujący rodzaj skrzyni biegów:", most_common_transmission)
print("Najczęściej spotykany typ właściciela:", most_common_owner_type)

print("\n")

# Histogram liczby samochodów dla każdego rodzaju paliwa
plt.figure(figsize=(8, 6))
df['Fuel_Type'].value_counts().plot(kind='bar', color='purple')
plt.title('Rozkład rodzaju paliwa')
plt.xlabel('Rodzaj paliwa')
plt.ylabel('Liczba samochodów')
plt.xticks(rotation=45)
plt.show()

print("\n")

# Wykres kołowy przedstawiający procentowy udział poszczególnych typów skrzyń biegów
plt.figure(figsize=(8, 8))
df['Transmission'].value_counts().plot(kind='pie', autopct='%1.1f%%', colors=['green', 'red'])
plt.title('Procentowy udział typów skrzyń biegów')
plt.ylabel('')
plt.show()

print("\n")

# Wykres liniowy przedstawiający rok produkcji samochodów w zależności od przebiegu
plt.figure(figsize=(10, 6))
sns.lineplot(x='Year', y='Kilometers_Driven', data=df)
plt.title('Zależność roku produkcji od przebiegu')
plt.xlabel('Rok produkcji')
plt.ylabel('Przebieg')
plt.show()

print("\n")

# Wykres słupkowy przedstawiający rozkład typów własności samochodów
plt.figure(figsize=(8, 6))
df['Owner_Type'].value_counts().plot(kind='bar', color='blue')
plt.title('Rozkład typów własności samochodów')
plt.xlabel('Typ własności')
plt.ylabel('Liczba samochodów')
plt.xticks(rotation=0)
plt.show()

print("\n")

# Wykres punktowy przedstawiający zależność między ceną a przebiegiem
plt.figure(figsize=(10, 6))
sns.scatterplot(x='Kilometers_Driven', y='Price', data=df, hue='Fuel_Type', palette='Set2', alpha=0.7)
plt.title('Zależność ceny od przebiegu')
plt.xlabel('Przebieg')
plt.ylabel('Cena')
plt.show()

print("\n")

# Wykres kołowy przedstawiający procentowy udział poszczególnych lokalizacji
plt.figure(figsize=(8, 8))
df['Location'].value_counts().plot(kind='pie', autopct='%1.1f%%', startangle=140, colors=sns.color_palette('tab10'))
plt.title('Procentowy udział lokalizacji')
plt.ylabel('')
plt.show()

print("\n")

# Wykres słupkowy przedstawiający rozkład liczby miejsc w samochodach
plt.figure(figsize=(8, 6))
df['Seats'].value_counts().sort_index().plot(kind='bar', color='teal')
plt.title('Rozkład liczby miejsc w samochodach')
plt.xlabel('Liczba miejsc')
plt.ylabel('Liczba samochodów')
plt.xticks(rotation=0)
plt.show()

print("\n")
