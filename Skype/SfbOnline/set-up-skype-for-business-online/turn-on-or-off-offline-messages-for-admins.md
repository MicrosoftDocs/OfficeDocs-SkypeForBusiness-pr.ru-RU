---
title: Включение и отключение отправки сообщений в автономном режиме для администраторов
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 3e083f7bf0d4f83ba5e904452721eaa92ed9e652
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962837"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="68505-103">Включение и отключение отправки сообщений в автономном режиме для администраторов</span><span class="sxs-lookup"><span data-stu-id="68505-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="68505-p101">[] Теперь можно отправлять сообщения Skype для бизнеса своим контактам, даже если они не вошли в приложение. Эта функция оповещает ваши контакты о том, что вы пытались с ними связаться. Больше не нужно ждать, пока пользователь зайдет в сеть, чтобы отправить ему сообщение.</span><span class="sxs-lookup"><span data-stu-id="68505-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="68505-107">Для сообщений в автономном режиме важно знать следующее:</span><span class="sxs-lookup"><span data-stu-id="68505-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="68505-108">Сообщения в автономном режиме не будут архивироваться в почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="68505-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="68505-109">Сообщения в автономном режиме будут отправлены в почтовый ящик пользователя, и пользователь получит уведомление, когда войдет в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="68505-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="68505-110">Если статус получателя сообщения **Не беспокоить** или **Идет презентация**, пользователь получит пропущенное сообщение с клиента Skype для бизнеса отправителя.</span><span class="sxs-lookup"><span data-stu-id="68505-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="68505-111">Дополнительные сведения см. в статье [Отправка сообщений в автономном режиме в Skype для бизнеса](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="68505-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="68505-112">Чтобы начать работу, можно сделать следующее</span><span class="sxs-lookup"><span data-stu-id="68505-112">To get you started</span></span>

## #

 <span data-ttu-id="68505-113">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="68505-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="68505-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="68505-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="68505-115">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="68505-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="68505-p102">Если у вас нет версии 3,0 или более новой, вам нужно скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Перезагрузите компьютер после появления соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="68505-p102">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="68505-p103">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="68505-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>

<span data-ttu-id="68505-122">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="68505-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="68505-123">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="68505-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="68505-124">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="68505-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="68505-125">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68505-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="68505-126">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="68505-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="68505-127">Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="68505-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="68505-128">Включение и отключение обмена мгновенными сообщениями в автономном режиме</span><span class="sxs-lookup"><span data-stu-id="68505-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="68505-129">Мгновенные сообщения в автономном режиме доступны **только** в последней версии клиента Skype для бизнеса с установкой "нажми и работай" и недоступны в более ранних версиях этого клиента, а также если для установки клиента Skype для бизнеса использовался MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="68505-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="68505-p104">Чтобы включить или отключить автономные сообщения, отправляемые пользователям в Организации, установите `True` для _EnableIMAutoArchiving_ значение или `False`. По умолчанию задано значение `True`.</span><span class="sxs-lookup"><span data-stu-id="68505-p104">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`. By default, this is set to `True`.</span></span>

<span data-ttu-id="68505-132">Чтобы отключить эту функцию, воспользуйтесь командлетом **Set-CsClientPolicy** и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68505-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="68505-p105">Чтобы включить или отключить автономные сообщения, отправляемые пользователю в автономном __ режиме, `True` установите `False`для EnableIMAutoArchiving значение или. По умолчанию задано значение `True`. Вы можете использовать существующую политику или создать ее, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="68505-p105">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`. By default, this is set to  `True`. You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="68505-136">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="68505-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="68505-p106">Windows PowerShell — это все, что нужно для управления пользователями, а также для пользователей, которым разрешено или не разрешено выполнять эти действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса Online с помощью одной точки администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Чтобы приступить к работе с Windows PowerShell, ознакомьтесь со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="68505-p106">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="68505-140">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="68505-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="68505-141">Шесть причин, по которым вам может потребоваться использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="68505-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="68505-p107">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей. Ознакомьтесь с этими преимуществами в указанных ниже разделах.</span><span class="sxs-lookup"><span data-stu-id="68505-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="68505-144">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="68505-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="68505-145">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="68505-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="68505-146">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="68505-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="68505-147">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="68505-147">Related topics</span></span>
[<span data-ttu-id="68505-148">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="68505-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="68505-149">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="68505-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


