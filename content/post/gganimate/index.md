---
title: Animasi Grafik dengan gganimate
summary:
date: 2021-10-27

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: "Image credit: [**Freepik**](https://www.freepik.com)"

authors:
  - admin

tags:
  - gganimate
  - R
  - ggplot2
---

Pada artikel ini akan dijelaskan step by step membuat animasi di R menggunakan packages [gganimate](https://rpubs.com/dedenistiawan/gganimate). [gganimate](https://rpubs.com/dedenistiawan/gganimate) adalah ekstensi dari packages [gglplot2](https://rpubs.com/dedenistiawan/gganimate) untuk membuat animasi. Untuk membuat animasi grafik dibutuhkan beberapa packages diantaranaya gapminder ggplot2 gganimate. [Read more](https://rpubs.com/dedenistiawan/gganimate)

## Load Package

    ```R
    library(gapminder)
    library(ggplot2)
    library(gganimate)
    ```

Tapap selanjutnya adalah import data dari gapminder di dalam dataset ini terdapat 1704 observasi dan 6 variabel. Variabel dalam dataset ini adalah:

1. Country adalah Nama Negara
2. Continent adalah Nama Benua
3. Year adalah Tahun dari setiap data
4. LifeExp adalah Angka harapan Hidup
5. Pop adalah Populasi setiap negara per tahun
6. gdpPercap adalah GDP per kapita setiap negara per tahun

## Import Data

    library(gapminder)
    library(ggplot2)
    library(gganimate)

## Membuat Plot Dasar Statis

sebelum membuat animasi, langkah awal adalah membuat plot dasar yang static dengan gglplot2 dan simpan gambar dengan nama gapminder_plot

    ```R
    library(gapminder)
    library(ggplot2)
    gapminder_plot <- ggplot(
      gapminder,
      aes(x = gdpPercap, y=lifeExp, size = pop, colour = continent, size = pop, frame = year)
      ) +
      geom_point(alpha = 0.6) +
      scale_color_viridis_d() +
      scale_x_log10() +
    labs(x = "GDP per capita", y = "Life expectancy")
    gapminder_plot
    ```

renders as

    ```R
    library(gapminder)
    library(ggplot2)
    gapminder_plot <- ggplot(
      gapminder,
      aes(x = gdpPercap, y=lifeExp, size = pop, colour = continent, size = pop, frame = year)
      ) +
      geom_point(alpha = 0.6) +
      scale_color_viridis_d() +
      scale_x_log10() +
    labs(x = "GDP per capita", y = "Life expectancy")
    gapminder_plot
    ```
