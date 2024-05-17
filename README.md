<img width="560" alt="image" src="https://github.com/Marsupilamieue/tutorial-11-advprog/assets/111985990/e824b7e7-2d31-4071-b24b-eed273ab9375"># tutorial-11-advprog

1. Compare the application logs before and after you exposed it as a Service.
Try to open the app several times while the proxy into the Service is running.
What do you see in the logs? Does the number of logs increase each time you open the app?

- Before
<img width="560" alt="image" src="https://github.com/Marsupilamieue/tutorial-11-advprog/assets/111985990/da368cf7-f352-4a9a-9da1-d7d1ada962fe">
- After
<img width="560" alt="image" src="https://github.com/Marsupilamieue/tutorial-11-advprog/assets/111985990/ecfc1d8a-8fe6-42b7-85c1-da11593f5fca">

  - Sebelum membuat service, pada logs hanya terdapat informasi bahwa server sudah berada pada port tertentu. Kemudian, setelah membuat service, di dalam logs terdapat informasi bahwa kita melakukan get pada service.


2. Notice that there are two versions of `kubectl get` invocation during this tutorial section.
The first does not have any option, while the latter has `-n` option with value set to
`kube-system`.
What is the purpose of the `-n` option and why did the output not list the pods/services that you
explicitly created?

  - Ketika menjalankan perintah kubectl get tanpa opsi `-n`, secara default akan mencari objek dalam namespace default. Dengan menambahkan opsi `-n` kube-system akan mengarahkan kubectl untuk mencari objek dalam namespace kube-system.

3. What is the difference between Rolling Update and Recreate deployment strategy?
> Hint: Read the Deployments documentation.
  - Rolling Update mengganti pod lama dengan yang baru secara bertahap, memastikan tidak ada downtime dan memungkinkan monitoring serta rollback yang mudah jika terjadi masalah. Sebaliknya, Recreate menghentikan semua pod lama sebelum memulai pod baru, menyebabkan downtime tetapi lebih sederhana dan menghindari konflik antara versi lama dan baru.
4. Try deploying the Spring Petclinic REST using Recreate deployment strategy and document
your attempt.
  - <img width="1066" alt="image" src="https://github.com/Marsupilamieue/tutorial-11-advprog/assets/111985990/8db0355f-768d-47a2-adf3-8d3e33dfb590">
  - <img width="918" alt="image" src="https://github.com/Marsupilamieue/tutorial-11-advprog/assets/111985990/5ef754e2-881f-4132-b13e-767428d74bf0">
  - Dalam tangkapan layar di atas, saya mencoba membuat deployment dan kemudian menghapusnya untuk menunjukkan metode recreate. Terlihat bahwa setelah penghapusan, pod baru dibuat. Selain itu, saya mencoba menjalankan dan melihat deployment melalui layanan sesuai instruksi dalam tutorial.
5. Prepare different manifest files for executing Recreate deployment strategy.
  - <img width="1036" alt="image" src="https://github.com/Marsupilamieue/tutorial-11-advprog/assets/111985990/82d0a7a9-c530-4fc5-b754-f936b883e8d7">
  - File manifest untuk strategi Recreate diberi nama deploymentRecreate.yaml. File ini sama seperti yang ada di tutorial, tetapi sekarang jenis strategi yang digunakan adalah Recreate
6. What do you think are the benefits of using Kubernetes manifest files?
  - Menurut saya, file manifest Kubernetes sangat membantu, terutama saat ingin membuat deployment. Dengan file manifest Kubernetes, saya tidak perlu mengulang lagi proses deployment. Saya hanya perlu menjalankan satu baris perintah `kubectl apply -f <nama_yaml.yaml>` yang akan membuat deployment, layanan, atau apa pun sesuai dengan konfigurasi dalam file YAML tersebut.

