---
title: Командлеты Lync Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online cmdlets
ms:assetid: 71f38305-fd8b-4013-83e1-cb742e3174c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362817(v=OCS.15)
ms:contentKeyID: 56558831
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1994843eb2059045525c61c5821051add2d30b47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-cmdlets"></a><span data-ttu-id="3de5b-102">Командлеты Lync Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-102">The Skype for Business Online cmdlets</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3de5b-103">_**Тема последнего изменения:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="3de5b-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="3de5b-104">Когда вы подключаетесь к Skype для бизнеса Online с помощью Windows PowerShell, набор командлетов Skype для бизнеса Online копируется в память компьютера.</span><span class="sxs-lookup"><span data-stu-id="3de5b-104">When you connect to Skype for Business Online by using Windows PowerShell, a collection of Skype for Business Online cmdlets is copied, in memory, to your computer.</span></span> <span data-ttu-id="3de5b-105">Эти командлеты наряду с любыми другими командлетами, уже установленными на локальном компьютере (в том числе с помощью основных командлетов, установленных при установке Windows PowerShell), можно использовать для управления развертыванием Skype для бизнеса Online и Skype для Учетные записи пользователей из бизнес-сети.</span><span class="sxs-lookup"><span data-stu-id="3de5b-105">These cmdlets, in addition to any other cmdlets you already have on your local computer (including the core cmdlets that are installed when you install Windows PowerShell), are then available for managing your Skype for Business Online deployment and your Skype for Business Online user accounts.</span></span> <span data-ttu-id="3de5b-106">Командлеты Skype для бизнеса Online представлены в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3de5b-106">The Skype for Business Online cmdlets are introduced in the following topics:</span></span>

  - [<span data-ttu-id="3de5b-107">Управление клиентами Lync Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-107">Managing Skype for Business Online tenants</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-skype-for-business-online-organizations)

  - [<span data-ttu-id="3de5b-108">Управление пользователями и свойствами учетной записи пользователя в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-108">Managing users and user account properties in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/user-accounts/user-accounts)

  - [<span data-ttu-id="3de5b-109">Управление политиками в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-109">Managing policies in Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-policies-with-office-365-powershell)

  - [<span data-ttu-id="3de5b-110">Управление клиентом Skype для бизнеса в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-110">Managing the Skype for Business client from Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365)

  - [<span data-ttu-id="3de5b-111">Управление единой системой обмена сообщениями Exchange и размещенной голосовой почтой в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-111">Managing Exchange Unified Messaging and hosted voice mail in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-exchange-unified-messaging-and-hosted-voicemail)

  - [<span data-ttu-id="3de5b-112">Управление связью в Skype для бизнеса Online с внешними пользователями и организациями</span><span class="sxs-lookup"><span data-stu-id="3de5b-112">Managing communications in Skype for Business Online with outside users and organizations</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users)

  - [<span data-ttu-id="3de5b-113">Управление встречами и конференциями Lync Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-113">Managing Skype for Business Online meetings and conferences</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/conferencing/conferencing-policies)

  - [<span data-ttu-id="3de5b-114">Управление сотовыми телефонами и мобильными устройствами в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-114">Managing cell phones and mobile devices in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/set-up-mobile-policies-for-your-organization)

<div>

## <a name="see-also"></a><span data-ttu-id="3de5b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3de5b-115">See Also</span></span>


[<span data-ttu-id="3de5b-116">Краткий справочник: использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Lync Online</span><span class="sxs-lookup"><span data-stu-id="3de5b-116">Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

