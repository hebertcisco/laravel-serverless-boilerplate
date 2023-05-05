<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

> It is important to note that this example can be improved, but it is an introductory example and I intend to bring more content of this type with more examples, consuming, for example, resources from cloud providers, such as SQS for queues, S3 for Storange, etc.

[*Serverless*](https://www.serverless.com/) applications are becoming increasingly popular due to their ability to automatically scale and reduce operational costs.

[**PHP**](https://www.php.net/) is a programming language widely used for web development and can be used to create efficient and scalable *Serverless* applications.

Using this kind of approach when providing a **PHP with Serverless** application, we have a very big gain in time, money and mainly, scalability.

However, with this, we will no longer, for example, pay a __fixed price__ for hosting, often with a fixed and small size of resources, such as memory and processing. In addition to the configuration being much more laborious and costing much more effort in a traditional hosting.

My example will use **PHP version 8.1** and the [Bref](https://bref.sh/) package. We will also use Laravel*, with a simple backend, with MySQL and Redis database.

To get started, it's important to have the PHP environment set up with Composer, and also Node.js installed, to ensure that our tutorial flows.

First, we must install the [*Serverless Framework*](https://www.serverless.com/) CLI, using the following command [NPM](https://nodejs.org/en/download):

```bash
npm install -g serverless
```

> It is important to note that _Bref_ is only compatible with versions above 3 of the Serverless Framework (which is the current version).

Have your [*AWS*](https://aws.amazon.com/pt/) credentials in hand so that we can proceed with the tutorial, where you will have to configure Serverless with your credentials with the following command:

```bash
serverless config credentials --provider aws --key <key> --secret <secret>
```

With that, we will create a common project with *Laravel*, using the `create-project` command by *composer*:

```bash
composer create-project laravel/laravel laravel-serverless-boilerplate
```
## Bref
With your new project open, install Laravel Bref using composer:
```
composer require bref/bref bref/laravel-bridge --update-with-dependencies
```

Now, with Bref installed, you will have Bref executables available within your vendor, knowing that, we will run the Bref initialization command:
```
php artisan vendor:publish --tag=serverless-config
```
## Deploy
Finally, we reached the final stretch, the implementation of this idea. To launch it, just run the commands below:
> We don't want to deploy "dev" caches that were generated on our machine (because the paths will be different in AWS Lambda). Let's clean up before going upstairs:
```bash
php artisan config:clear
```

> When running on AWS Lambda, the Laravel application will automatically cache its configuration during startup. You don't need to run php crafter config:cache before deploying.

 ```bash
serverless deploy
```

When finished, the `deploy` command will show the URL of the application.

Know that this is the basics, this *Serverless* configuration is minimal and can be extended and adapted to your needs. So if you want to deploy to production or learn more about *Serverless*, follow me on YouTube for more content, (I want to create more related content)

## Links
- [Sample repository](https://github.com/hebertcisco/laravel-serverless-boilerplate)
- [My channel](https://www.youtube.com/channel/UCIXLXWPLZUWUa8tJ8c8EeKg)
- [How to Host a Node.js Backend on Vercel](https://www.youtube.com/watch?v=Y-RoNF3Hd7I)
- [Deploying Python API (FastApi) on Vercel](https://www.youtube.com/watch?v=r5VfItbTAt8)
- [Serverless Framework](https://www.serverless.com/framework/docs/getting-started)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](issues).

## Show your support

Give a ⭐️ if this project helped you!

Or buy me a coffee 🙌🏾

<a href="https://www.buymeacoffee.com/hebertcisco">
    <img src="https://img.buymeacoffee.com/button-api/?text=Buy me a coffee&emoji=&slug=hebertcisco&button_colour=FFDD00&font_colour=000000&font_family=Inter&outline_colour=000000&coffee_colour=ffffff" />
</a>

## 📝 License

Copyright © 2023 [Hebert F Barros](https://github.com/hebertcisco).<br />
This project is [MIT](LICENSE) licensed.
