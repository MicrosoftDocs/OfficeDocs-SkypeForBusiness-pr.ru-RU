---
title: 'Lync Server 2013: настройка паролей учетных записей проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ca8bf5d1b3dc90b1ceacbe581e0426b5c0aaa9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="501be-102">Настройка паролей учетных записей проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="501be-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="501be-103">_**Тема последнего изменения:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="501be-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="501be-104">После того как вы создадите объект компьютера для учетной записи проверки подлинности Kerberos, вы можете настроить пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="501be-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="501be-105">Вы запускаете командлет Windows PowerShell для задания пароля учетной записи Kerberos на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="501be-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="501be-106">Вы можете установить пароль для объекта, созданного для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="501be-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="501be-107">Для пароля может быть задано известное значение, но по умолчанию используется случайный пароль.</span><span class="sxs-lookup"><span data-stu-id="501be-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="501be-108">Пароль доступен для всех источников проверки подлинности Kerberos, использующих эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="501be-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="501be-109">Вы можете использовать командлеты Windows PowerShell для настройки и управления паролями учетной записи Kerberos.</span><span class="sxs-lookup"><span data-stu-id="501be-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="501be-110">Объект учетной записи Kerberos является объектом компьютера, но использует параметр UserAccount для операций в командлетах Windows PowerShell, на которые указывают ссылки.</span><span class="sxs-lookup"><span data-stu-id="501be-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="501be-111">Обратите внимание, что это не ошибка, но предполагаемое поведение командлета при создании и обслуживании учетной записи Kerberos.</span><span class="sxs-lookup"><span data-stu-id="501be-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="501be-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="501be-112">In This Section</span></span>

  - [<span data-ttu-id="501be-113">Установка пароля учетной записи Kerberos для проверки подлинности на сервере в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="501be-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="501be-114">Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="501be-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

