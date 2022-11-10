# GOLANG CONTEXT
salah satu fungsinya untuk menghidari Goroutine leak

## Parent & Child Context
- Saat membuat context, kita bisa membuat child context dari context yang sudah ada
- Parent context bisa memiliki banyak child, namun child hanya bisa memiliki satu parent context
- Konsep ini mirip dengan pewarisan di pemrograman berientasi object
- Ketika parent di cancel maka semua child nya akan di cancel juga
- Sifatnya immutable (sekali di-set datanya tidak dapat diubah), ketika ditambahkan value baru makan akan menjadi context (chid) baru

## Context with value
- kita bisa menambah value dengan data Pair (key: value)
- context child bisa baca value parent, tapi tidak sebaliknya

## Context with cancel
- menciptakan context baru, bukan mengubah context yg sudah ada

## Context with timeout
- sangat cocok ketika melakukan query database atau untuk http api, namun ingin menentukan batas maksimal timeoutnya
- menggunakan context.WithTimeout(parent, duration)

## Context with deadline
- pengaturan deadline ditentukan kapan waktu timeout nya, misal jam 12 siang hari ini
- context.WithDeadline(parent, time)