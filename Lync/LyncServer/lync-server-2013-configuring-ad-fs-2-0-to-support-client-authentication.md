---
title: 'Lync Server 2013: настройка AD FS 2,0 для поддержки проверки подлинности клиента'
description: 'Lync Server 2013: настройка AD FS 2,0 для поддержки проверки подлинности клиента.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156eb6d7e8af85dec04601ab8f88c55181db20d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553255"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="26589-103">Настройка служб федерации Active Directory 2,0 для поддержки проверки подлинности клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26589-103">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26589-104">_**Последнее изменение темы:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="26589-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="26589-105">Существует два типа проверки подлинности, которые можно настроить, чтобы разрешить AD FS 2,0 поддерживать проверку подлинности с помощью смарт-карт:</span><span class="sxs-lookup"><span data-stu-id="26589-105">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="26589-106">Проверка подлинности на основе форм (FBA)</span><span class="sxs-lookup"><span data-stu-id="26589-106">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="26589-107">Проверка подлинности клиента для TLS</span><span class="sxs-lookup"><span data-stu-id="26589-107">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="26589-108">С помощью проверки подлинности на основе форм можно разработать веб-страницу, которая позволит пользователям проходить проверку подлинности с помощью имени пользователя и пароля, а также с помощью смарт-карты и ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="26589-108">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="26589-109">В этом разделе рассказывается, как реализовать проверку подлинности клиентов TLS с помощью служб федерации Active Directory 2,0.</span><span class="sxs-lookup"><span data-stu-id="26589-109">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="26589-110">Дополнительные сведения о типах проверки подлинности AD FS 2,0 приведены в статье AD FS 2,0: как изменить тип локальной проверки подлинности по адресу [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) .</span><span class="sxs-lookup"><span data-stu-id="26589-110">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="26589-111">**Настройка AD FS 2,0 для поддержки проверки подлинности клиента**</span><span class="sxs-lookup"><span data-stu-id="26589-111">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="26589-112">Выполните вход на компьютер с AD FS 2,0 с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="26589-112">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="26589-113">Запустите проводник Windows.</span><span class="sxs-lookup"><span data-stu-id="26589-113">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="26589-114">Переход на C: \\ Inetpub \\ ADFS \\ Ls</span><span class="sxs-lookup"><span data-stu-id="26589-114">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="26589-115">Создайте резервную копию существующего файла web.config.</span><span class="sxs-lookup"><span data-stu-id="26589-115">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="26589-116">Откройте существующий web.config файл с помощью блокнота.</span><span class="sxs-lookup"><span data-stu-id="26589-116">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="26589-117">В строке меню выберите команду **изменить** , а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="26589-117">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="26589-118">Выполните поиск **\<localAuthenticationTypes\>** .</span><span class="sxs-lookup"><span data-stu-id="26589-118">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="26589-119">Обратите внимание на то, что указаны четыре типа проверки подлинности, по одному в строке.</span><span class="sxs-lookup"><span data-stu-id="26589-119">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="26589-120">Переместите строку, содержащую тип проверки подлинности Тлсклиент, в верхнюю часть списка в разделе.</span><span class="sxs-lookup"><span data-stu-id="26589-120">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="26589-121">Сохраните и закройте файл web.config.</span><span class="sxs-lookup"><span data-stu-id="26589-121">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="26589-122">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="26589-122">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="26589-123">Перезапустите службы IIS, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="26589-123">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

