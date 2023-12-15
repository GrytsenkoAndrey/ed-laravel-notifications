# ed-laravel-notifications
by article https://medium.com/@microDesignn/using-laravel-notifications-in-your-project-a-step-by-step-guide-bb9704420da1

## introduction

Laravel, known for its elegant syntax and comprehensive feature set, includes a powerful notification system that allows developers to send a variety of notifications via multiple channels. Notifications can be used to inform users about various events in your application, like new messages, friend requests, or system updates. This guide will walk you through how to leverage Laravel Notifications in your project.
Understanding Laravel Notifications

Laravel’s notification system is versatile, allowing for notifications to be sent via email, SMS (via Nexmo), Slack, and more. Notifications can be stored in a database, broadcast over websockets, or simply logged.

## Step 1: Setting Up Your Laravel Environment

Before you start, ensure you have a Laravel project set up. If not, you can create a new one using Composer:

composer create-project --prefer-dist laravel/laravel YourProjectName

Step 2: Creating Notifications

To create a notification, use the make:notification Artisan command:

php artisan make:notification InvoicePaid

This command creates a new InvoicePaid notification class in the app/Notifications directory.
Step 3: Writing Notification Class

In your notification class, you can define several methods corresponding to the channels the notification will be sent through. For example:

    via() method defines the channels.
    toMail() for sending email notifications.
    toDatabase() for storing notifications in the database.

Step 4: Sending Notifications

You can send notifications to Notifiable entities, such as users. First, ensure that your user class uses the Notifiable trait. Then, you can send a notification like this:

```
$user->notify(new InvoicePaid($invoice));
```
