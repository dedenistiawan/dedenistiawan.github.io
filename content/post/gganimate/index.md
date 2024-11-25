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

Pada artikel ini akan dijelaskan step by step membuat animasi di R menggunakan packages [gganimate](https://rpubs.com/dedenistiawan/gganimate). [gganimate](https://rpubs.com/dedenistiawan/gganimate) adalah ekstensi dari packages [gglplot2](https://rpubs.com/dedenistiawan/gganimate) untuk membuat animasi. Untuk membuat animasi grafik dibutuhkan beberapa packages diantaranaya gapminder ggplot2 gganimate. [Read more](https://rpubs.com/dedenistiawan/gganimate).

## Load Package

    library(gapminder)
    library(ggplot2)
    library(gganimate)

Tapap selanjutnya adalah import data dari gapminder di dalam dataset ini terdapat 1704 observasi dan 6 variabel. Variabel dalam dataset ini adalah:

1. Country adalah Nama Negara
2. Continent adalah Nama Benua
3. Year adalah Tahun dari setiap data
4. LifeExp adalah Angka harapan Hidup
5. Pop adalah Populasi setiap negara per tahun
6. gdpPercap adalah GDP per kapita setiap negara per tahun

## Import Data

    library(gapminder)
    data=gapminder
    data

## Membuat Plot Dasar Statis

sebelum membuat animasi, langkah awal adalah membuat plot dasar yang static dengan gglplot2 dan simpan gambar dengan nama gapminder_plot

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

## Menambahkan Transisi

    library(gganimate)
    gapminder_plot + transition_time(year) +
      labs(title = "Year: {frame_time}")

## Membuat Plot Tiap Benua

    library(gganimate)
    gapminder_plot + facet_wrap(~continent) +
      transition_time(year) +
      labs(title = "Year: {frame_time}")

## Membuat Plot Dinamis

    library(gganimate)
    gapminder_plot + transition_time(year) +
      labs(title = "Year: {frame_time}") +
      view_follow(fixed_y = TRUE)

## Membuat Bayanga Animasi

    library(gganimate)
    gapminder_plot + transition_time(year) +
      labs(title = "Year: {frame_time}") +
      shadow_wake(wake_length = 0.1, alpha = FALSE)

## Menampilkan Jejak Data

    library(gganimate)
    gapminder_plot + transition_time(year) +
      labs(title = "Year: {frame_time}") +
      shadow_mark(alpha = 0.3, size = 0.5)

```latex
$$
\gamma_{n} = \frac{ \left | \left (\mathbf x_{n} - \mathbf x_{n-1} \right )^T \left [\nabla F (\mathbf x_{n}) - \nabla F (\mathbf x_{n-1}) \right ] \right |}{\left \|\nabla F(\mathbf{x}_{n}) - \nabla F(\mathbf{x}_{n-1}) \right \|^2}
$$
```

renders as

$$\gamma_{n} = \frac{ \left | \left (\mathbf x_{n} - \mathbf x_{n-1} \right )^T \left [\nabla F (\mathbf x_{n}) - \nabla F (\mathbf x_{n-1}) \right ] \right |}{\left \|\nabla F(\mathbf{x}_{n}) - \nabla F(\mathbf{x}_{n-1}) \right \|^2}$$
