---
title: 'Lync Server 2013: Администрирование пользователей в гибридном развертывании'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03819bdf387c426c3a0bda5074ad0a36021f68c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="06fd1-102">Администрирование пользователей в гибридном развертывании Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06fd1-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06fd1-103">_**Последнее изменение темы:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="06fd1-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="06fd1-104">Вы можете управлять параметрами пользователей и политиками для пользователей, перенесенных в Lync Online, используя функции управления пользователями, доступные на портале Microsoft Office 365 Online.</span><span class="sxs-lookup"><span data-stu-id="06fd1-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="06fd1-105">Для выполнения задач администрирования необходимо войти в систему с помощью учетной записи администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="06fd1-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="06fd1-106">Возврат пользователей в локальную среду</span><span class="sxs-lookup"><span data-stu-id="06fd1-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="06fd1-107">Этот раздел относится только к пользователям, созданным и включенным в локальной среде Lync, а затем перемещению из локального развертывания в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="06fd1-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="06fd1-108">Если вы хотите переместить пользователей, созданных в Lync Online (и не включенных для Lync в локальном развертывании), ознакомьтесь со статьей <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Перемещение пользователей из Lync Online в локальную среду Lync в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="06fd1-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="06fd1-109">Выполните следующие командлеты, чтобы переместить пользователя из Lync Online обратно в локальную среду Lync:</span><span class="sxs-lookup"><span data-stu-id="06fd1-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="06fd1-110">Формат URL-адреса, указанный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, в котором запущена служба переноса, в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="06fd1-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="06fd1-111">Полное\<доменное\>имя пула HTTPS:///HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="06fd1-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="06fd1-112">Вы можете определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для своей учетной записи клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="06fd1-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="06fd1-113">**Определение размещенного URL-адреса службы миграции для клиента Office 365**</span><span class="sxs-lookup"><span data-stu-id="06fd1-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="06fd1-114">Войдите в свой клиент Office 365 от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="06fd1-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="06fd1-115">Откройте **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="06fd1-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="06fd1-116">При отображении **центра администрирования Lync** выберите и скопируйте URL-адрес в адресную строку вплоть до **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="06fd1-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="06fd1-117">Пример URL-адреса выглядит примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="06fd1-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="06fd1-118">Замените **webdir** в URL-адресе на **"Администратор"**, что приводит к следующим действиям:</span><span class="sxs-lookup"><span data-stu-id="06fd1-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="06fd1-119">Добавьте указанную ниже строку в URL-адрес: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="06fd1-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="06fd1-120">Итоговый URL-адрес, который является значением **хостедмигратионоверридеурл**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="06fd1-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

