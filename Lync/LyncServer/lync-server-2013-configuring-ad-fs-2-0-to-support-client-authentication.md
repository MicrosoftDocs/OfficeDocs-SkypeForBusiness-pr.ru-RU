---
title: 'Lync Server 2013: настройка AD FS 2,0 для поддержки проверки подлинности клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="a49d0-102">Настройка службы AD FS 2,0 для поддержки проверки подлинности клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a49d0-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a49d0-103">_**Тема последнего изменения:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="a49d0-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="a49d0-104">Чтобы разрешить в AD FS 2.0 поддержку проверки подлинности с использованием смарт-карт, можно настроить два указанных ниже типа проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a49d0-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="a49d0-105">Проверка подлинности на основе форм</span><span class="sxs-lookup"><span data-stu-id="a49d0-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="a49d0-106">Проверка подлинности клиента по протоколу TLS</span><span class="sxs-lookup"><span data-stu-id="a49d0-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="a49d0-107">На основе проверки подлинности по формам можно разработать веб-страницу, где подлинность пользователей будет проверяться по имени и паролю или по смарт-карте и PIN‑коду.</span><span class="sxs-lookup"><span data-stu-id="a49d0-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="a49d0-108">В этой статье рассматривается преимущественно реализация проверки подлинности клиента по протоколу TLS с помощью AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="a49d0-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="a49d0-109">Дополнительные сведения о типах проверки подлинности AD FS 2,0 можно найти в статье AD FS 2,0: как изменить тип локальной [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)проверки подлинности по адресу.</span><span class="sxs-lookup"><span data-stu-id="a49d0-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="a49d0-110">**Настройка AD FS 2.0 для поддержки проверки подлинности клиента**</span><span class="sxs-lookup"><span data-stu-id="a49d0-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="a49d0-111">Войдите в систему на компьютере с AD FS 2.0 с помощью учетной записи администратора домена.</span><span class="sxs-lookup"><span data-stu-id="a49d0-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="a49d0-112">Запустите проводник.</span><span class="sxs-lookup"><span data-stu-id="a49d0-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="a49d0-113">Переход на C:\\инетпуб\\ADFS\\Ls</span><span class="sxs-lookup"><span data-stu-id="a49d0-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="a49d0-114">Сделайте резервную копию файла web.config.</span><span class="sxs-lookup"><span data-stu-id="a49d0-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="a49d0-115">Откройте файл web.config с помощью Блокнота.</span><span class="sxs-lookup"><span data-stu-id="a49d0-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="a49d0-116">В строке меню выберите **Правка**, затем **Найти**.</span><span class="sxs-lookup"><span data-stu-id="a49d0-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="a49d0-117">Поиск \*\* \<локалаусентикатионтипес\>\*\*.</span><span class="sxs-lookup"><span data-stu-id="a49d0-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="a49d0-118">Обратите внимание, что здесь будут перечислены четыре типа проверки подлинности, по одному на строку.</span><span class="sxs-lookup"><span data-stu-id="a49d0-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="a49d0-119">Переместите строку, содержащую тип проверки подлинности TLSClient, в начало списка в разделе.</span><span class="sxs-lookup"><span data-stu-id="a49d0-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="a49d0-120">Сохраните и закройте файл web.config.</span><span class="sxs-lookup"><span data-stu-id="a49d0-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="a49d0-121">Запустите командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="a49d0-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="a49d0-122">Перезапустите службу IIS, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a49d0-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

