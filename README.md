## Quick Push Notification Integration In Ionic + Capacitor (React)

### Requirements:

- Create a FREE [OneSignal](https://onesignal.com/) account
- Create an Web Push App inside of the OneSignal Dashboard
- Follow the steps of the [Typical setup](https://documentation.onesignal.com/docs/web-push-typical-setup)
- This tutorial requires some basic knowledge on React
- [Ionic CLI](https://ionicframework.com/docs/cli) version 6.16.3
- NodeJS version 14.0

### Repo:

- [Quick setup](https://github.com/OneSignal/OneSignal-Angular)
- [Advanced setup](https://github.com/OneSignal/OneSignal-Angular/tree/FINAL-CODE)

Creating Your Ionic + Capacitor (React) App
Inside your terminal, you will have to run the following command to add the Ionic project globally in your machine to use Ionic in your command line.

```shell
npm install -g @ionic/cli
```

Inside of your terminal run the following command to create a new Ionic + Capacitor (React) project using the Ionic CLI. You will be asked to select a framework, select React.

```shell
ionic start
```

![ionic start](https://lh4.googleusercontent.com/nk9cGFqNqXSTF7aFV37Rz-5SYECE1ho1W76H_mJ--OnVBu_jJF4ML5ez7Jxls6AdOSwLYsI5jePyTacXvvT_Qc77j8vCH0fnU5p5GUObkKWLaNDsq2F1MXP6FQ7v1xEpq3e-fhIk)

When asked to enter a project name, you can enter whatever name you want. In my case, I named my project ​​**OneSignal-Ionic**.

![Ionic project name](https://lh6.googleusercontent.com/zJdh-WIrO9GpGSi_J_5TIBdWDefEJD3Gg0rLx_Xf9vha4WPTLwjvDlNUbJDsfbtXBSitJiTdn6VrGwDSmCR0S8k_8HoVqy_3FCPQnlq1zPz94aXv0PD5IxWSDZemoSuk31PrEAYu)

Later you will be asked to select a template, feel free to select the template that you want. In my case, I will be selecting **tabs**.

![ionic tabs template](https://lh3.googleusercontent.com/6WJKyp8p393BnpXuKcq50Lf2DhKOl7Xrw6yUXyAl7qhE66xFzePN2Kw0YfsoP7lcxGOXVluwPtYiYlyUNbSEJP-8D0clLmgGtvhBAqRT5sYLdYRS1W_L6OmmIHQlkynQ9m-NHfaj)

### Quick OneSignal Setup In Ionic Application

In your Ionic project folder, navigate to the public folder and open the **index.html** file. Inside of the head HTML tag paste the following code (This is the same code you copied form the typic site setup steps).

```html
<script src="https://cdn.onesignal.com/sdks/OneSignalSDK.js" async=""></script>
<script>
  window.OneSignal = window.OneSignal || [];
  OneSignal.push(function () {
    OneSignal.init({
      appId: "YOUR-APP-ID",
    });
  });
</script>
```

Now, [download the SDK files](https://github.com/OneSignal/OneSignal-Website-SDK/releases/download/https-integration-files/OneSignal-Web-SDK-HTTPS-Integration-Files.zip) in your computer and insert them inside of the _public_ folder of your Ionic app.

![OneSignal SDK files](https://lh6.googleusercontent.com/k2BoFHAeerxCWiMuXotSISlVC_ztUaUj2_PDGwRpdsSTSkz3PB3fpE79wcWMWLusvRhihDnZvQVU-DbTcoIsPXB68UUcY1Vto3QasIAShwv2CXS66_3fY_kUNHH-BLrji3qMd90X)
