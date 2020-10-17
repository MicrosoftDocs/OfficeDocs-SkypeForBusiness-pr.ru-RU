---
title: 'Lync Server 2013: Настройка паролей учетных записей проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29e8887f35e6d60d7d3aa59a0aa05590df371618
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509676"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="b7311-102">Настройка паролей учетных записей проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7311-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7311-103">_**Последнее изменение темы:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="b7311-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="b7311-104">После создания объекта-компьютера для учетной записи проверки подлинности Kerberos можно задать пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b7311-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="b7311-105">Для задания пароля учетной записи Kerberos на одном сервере выполните командлет Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7311-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="b7311-106">Кроме того, можно задать пароль для объекта, созданного для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b7311-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="b7311-107">В качестве пароля можно использовать известное значение, однако по умолчанию используется случайный пароль.</span><span class="sxs-lookup"><span data-stu-id="b7311-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="b7311-108">Пароль доступен всем источникам проверки подлинности Kerberos, которые используют учетную запись.</span><span class="sxs-lookup"><span data-stu-id="b7311-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="b7311-109">Командлеты Windows PowerShell используются для настройки паролей учетных записей Kerberos и управления ими.</span><span class="sxs-lookup"><span data-stu-id="b7311-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7311-110">Объект учетной записи Kerberos является объектом Computer, но использует параметр UserAccount для операций в командлетах Windows PowerShell, на которые указывают ссылки.</span><span class="sxs-lookup"><span data-stu-id="b7311-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="b7311-111">Обратите внимание, что это не ошибка, а намеренное поведение командлета при использовании с учетной записью создания и поддержки Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b7311-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b7311-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="b7311-112">In This Section</span></span>

  - [<span data-ttu-id="b7311-113">Установка пароля учетной записи проверки подлинности Kerberos на сервере в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7311-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="b7311-114">Синхронизация пароля учетной записи проверки подлинности Kerberos с IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7311-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

