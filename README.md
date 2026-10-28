# ServiceBusDemo

A simple .NET console application that sends a message to an **Azure Service Bus** queue.

Built as part of the course **Microsoft Azure From Zero to Hero - The Complete Guide**.

## Overview

The application:

1. Creates a `ServiceBusClient` using a Service Bus connection string.
2. Creates a `ServiceBusSender` for the queue `my-items`.
3. Sends a single message (`"Test Message"`) to the queue.
4. Waits for the user to press **ENTER** before exiting.

## Tech Stack

- .NET 10 (console app)
- [Azure.Messaging.ServiceBus](https://www.nuget.org/packages/Azure.Messaging.ServiceBus) 7.0.0

## Prerequisites

- [.NET SDK 10](https://dotnet.microsoft.com/download)
- An Azure subscription
- An Azure Service Bus namespace with a queue named `my-items`

## Azure Setup

1. In the Azure Portal, create a **Service Bus Namespace**.
2. Inside the namespace, create a **Queue** named `my-items`.
3. Open **Shared access policies**, select a policy with **Send** permission, and copy its **Primary Connection String**.

## Configuration

In `Program.cs`, set the connection string and queue name:

```csharp
public static string connectionString = "<YOUR_SERVICE_BUS_CONNECTION_STRING>";
public static string queueName = "my-items";
```

## Run

```bash
dotnet restore
dotnet run
```

Expected output:

```
======================================================
Press ENTER key to exit after sending all the messages.
======================================================
Sent a single message to the queue: my-items
```

You can verify the message in the Azure Portal using **Service Bus Explorer** on the `my-items` queue.

## Project Structure

```
ServiceBusDemo/
├── Program.cs              # Sends a message to the Service Bus queue
├── ServiceBusDemo.csproj   # Project file and package references
└── README.md
```
