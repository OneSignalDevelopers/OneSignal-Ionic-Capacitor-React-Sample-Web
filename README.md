## Push Notification Integration In Ionic + Capacitor Web App (React)

### Requirements:

- Create a FREE [OneSignal](https://onesignal.com/) account
- Create an Web Push App inside of the OneSignal Dashboard
- Follow the steps of the [Typical setup](https://documentation.onesignal.com/docs/web-push-typical-setup)
- This tutorial requires some basic knowledge on React
- [Ionic CLI](https://ionicframework.com/docs/cli) version 6.16.3
- NodeJS version 14.0

### Setup:

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

### Adding OneSignal To Your Ionic Capacitor Application

In your Ionic project folder, navigate to the public folder and locate the **SDK files you downloaded** on your computer and **insert** them inside your Ionic app’s **public** folder.

If you need to, you can re-download the [OneSignal SDK files](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://github.com/OneSignal/OneSignal-Website-SDK/releases/download/https-integration-files/OneSignal-Web-SDK-HTTPS-Integration-Files.zip%26sa%3DD%26source%3Deditors%26ust%3D1628702959272016%26usg%3DAOvVaw20AWvJUAnZOK45U66QbMzI&sa=D&source=editors&ust=1628797158235000&usg=AOvVaw297U7nxBGRFEMWyullCqd5).

![ionic project structure](https://lh6.googleusercontent.com/k2BoFHAeerxCWiMuXotSISlVC_ztUaUj2_PDGwRpdsSTSkz3PB3fpE79wcWMWLusvRhihDnZvQVU-DbTcoIsPXB68UUcY1Vto3QasIAShwv2CXS66_3fY_kUNHH-BLrji3qMd90X=s0)

#### Install React-OneSignal NPM package

Inside of your project folder, open your terminal and run the following command to install the [React OneSignal NPM](https://www.npmjs.com/package/react-onesignal) package.

```javascript
npm i react-onesignal
```

After you have successfully installed the npm package, open your **App.tsx** file, you will enter the following line of code at the top of the file:

```javascript
import OneSignal from "react-onesignal";
```

The code above will make the OneSignal object accessible and will allow you to have access to the OneSignal SDK properties.
In the same file, we will create a `useEffect` hook. This hook will have the initialization code needed to trigger OneSignal. Remember to add the dependency array `[]` to your `useEffect` hook. The [init()](https://www.npmjs.com/package/react-onesignal) method from OneSignal can only be called once and the dependency array will help us to avoid that the `useEffect` gets triggered multiple times firing the `init()` method.

```javascript
useEffect(() => {
   OneSignal.init({
     appId: "YOUR-APP-ID-HERE"
   });
 }, []);
```

In the **appId propety** insert the OneSignal **App ID** you saved somewhere in your computer.

