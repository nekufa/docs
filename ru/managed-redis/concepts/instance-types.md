# Классы хостов

Класс хостов определяет вычислительные мощности, которые выделяются для каждого хоста в кластере. При изменении класса хостов для кластера меняются характеристики всех уже созданных в нем хостов.

{% note info %}

Выделенный для хоста объем памяти также определяет параметр конфигурации `maxmemory` для хостов Redis: максимальный объем данных равен 75% доступной памяти. Например, для хоста с 8 ГБ памяти значение `maxmemory` будет установлено в 6 ГБ.

{% endnote %}

Размер доступного хосту жесткого диска должен как минимум в два раза превышать выбранный объем памяти. Технические и организационные ограничения {{ mrd-name }} приведены в разделе [{#T}](limits.md).

Доступный объем хранилища не зависит от класса хостов.  Ограничения хранилища приведены в разделе [{#T}](limits.md).

## Доступные классы хостов {#available-flavors}

Типы конфигураций:

* **b1, b2** — конфигурации с [гарантированной долей vCPU](../../compute/concepts/performance-levels.md) ниже 100%. Эти классы хостов предназначены для тестовой нагрузки, для продакшн-решений их использовать не рекомендуется.
* **hm1, hm2** — стандартные конфигурации для {{ RD }}.

Имя класса хостов | RAM, ГБ | Размер диска, ГБ
----- | ----- | -----
b1.nano | 2 | 4 - 16
b1.small | 4 | 8 - 32
hm1.nano | 8 | 16 - 64
hm1.micro | 12 | 24 - 96
hm1.small | 16 | 32 - 128
hm1.medium | 24 | 48 - 192
hm1.large | 32 | 64 - 256
hm1.xlarge | 48 | 96 - 384
hm1.2xlarge | 64 | 128 - 512
hm1.3xlarge | 80 | 160 - 640
hm1.4xlarge | 96 | 192 - 768
hm1.5xlarge | 128 | 256 - 1024
hm1.6xlarge | 160 | 320 - 1280
hm1.7xlarge | 192 | 384 - 1536
hm1.8xlarge | 224 | 448 - 1792
hm1.9xlarge | 256 | 512 - 2048
