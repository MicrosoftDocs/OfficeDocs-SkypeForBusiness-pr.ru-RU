---
title: 'Lync Server 2013: Администрирование пользователей в гибридном развертывании'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd4f53eaa611d130291b1a42c798a8d5589968c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="3c4ab-102">Администрирование пользователей в гибридном развертывании Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c4ab-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c4ab-103">_**Тема последнего изменения:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="3c4ab-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="3c4ab-104">Вы можете управлять параметрами пользователей и политиками для пользователей, перенесенных на Lync Online с помощью функций управления пользователями, доступных на портале Microsoft Office 365 Online.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="3c4ab-105">Для выполнения задач администрирования необходимо войти по учетной записи администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="3c4ab-106">Перемещение пользователей на локальный сервер</span><span class="sxs-lookup"><span data-stu-id="3c4ab-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="3c4ab-107">Этот раздел относится только к пользователям, которые были созданы и включены в локальной среде Lync, а затем перенесено из локального развертывания в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="3c4ab-108">Если вы хотите переместить пользователей, которые были созданы в Lync Online (и не включены для Lync в локальном развертывании), ознакомьтесь с разрешениями: <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Перемещение пользователей из Lync Online в локальное приложение Lync в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="3c4ab-109">Чтобы переместить пользователя из Lync Online обратно в локальное Lync, выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="3c4ab-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```
        $cred=Get-Credential
       ```
    
       ```
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="3c4ab-110">В качестве параметра **HostedMigrationOverrideUrl** следует указать URL-адрес пула, где работает служба миграции с размещением, в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="3c4ab-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="3c4ab-111">Полное\<доменное\>имя пула HTTPS:///хостедмигратион/хостедмигратионсервице.СВК.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="3c4ab-112">URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="3c4ab-113">**Определение URL-адреса размещенной службы миграции для своего клиента Office 365**</span><span class="sxs-lookup"><span data-stu-id="3c4ab-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="3c4ab-114">Выполните вход в свое клиентское приложение Office 365 как администратор.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="3c4ab-115">Откройте **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="3c4ab-116">В **центре администрирования Lync** выберите и скопируйте URL-адрес в адресной строке на **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="3c4ab-117">Ниже показан возможны пример URL-адреса</span><span class="sxs-lookup"><span data-stu-id="3c4ab-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="3c4ab-118">После замены фрагмента **webdir** в URL-адресе фрагментом **admin** получается следующий результат:</span><span class="sxs-lookup"><span data-stu-id="3c4ab-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="3c4ab-119">Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="3c4ab-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="3c4ab-120">Итоговый URL-адрес, который служит значением параметра **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3c4ab-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

