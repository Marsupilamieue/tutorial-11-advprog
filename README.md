# tutorial-11-advprog

1. Compare the application logs before and after you exposed it as a Service.
Try to open the app several times while the proxy into the Service is running.
What do you see in the logs? Does the number of logs increase each time you open the app?
  - Sebelum membuat service, pada logs hanya terdapat informasi bahwa server sudah berada pada port tertentu. Kemudian, setelah membuat service, di dalam logs terdapat informasi bahwa kita melakukan get pada service.


2. Notice that there are two versions of `kubectl get` invocation during this tutorial section.
The first does not have any option, while the latter has `-n` option with value set to
`kube-system`.
What is the purpose of the `-n` option and why did the output not list the pods/services that you
explicitly created?

Ketika menjalankan perintah kubectl get tanpa opsi `-n`, secara default akan mencari objek dalam namespace default. Dengan menambahkan opsi `-n` kube-system akan mengarahkan kubectl untuk mencari objek dalam namespace kube-system.

