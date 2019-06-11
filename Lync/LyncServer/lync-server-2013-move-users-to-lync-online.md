---
title: 'Lync Server 2013: перемещение пользователей в Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 410fd1fe521bd8d4750b290a54db26adb630a8be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="162fe-102">Перемещение пользователей в Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="162fe-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="162fe-103">_**Тема последнего изменения:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="162fe-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="162fe-104">Прежде чем приступить к переносу пользователей на Lync Online, необходимо создать резервную копию данных пользователя, связанных с учетными записями, которые нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="162fe-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="162fe-105">Вместе с учетной записью перемещаются не все данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="162fe-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="162fe-106">Дополнительные сведения можно найти [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="162fe-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="162fe-107">Перенос параметров пользователя в Lync Online</span><span class="sxs-lookup"><span data-stu-id="162fe-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="162fe-108">Параметры пользователя перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="162fe-108">User settings are moved with the user account.</span></span> <span data-ttu-id="162fe-109">Некоторые локальные параметры не перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="162fe-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="162fe-110">Перемещение пилотных пользователей в Lync Online</span><span class="sxs-lookup"><span data-stu-id="162fe-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="162fe-111">Прежде чем приступить к перемещению пользователей на Lync Online, вам может потребоваться переместить нескольких пилотных пользователей, чтобы убедиться, что ваша среда настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="162fe-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="162fe-112">Вы можете проверить, что функции и службы Lync будут работать должным образом, прежде чем переходить к перемещению других пользователей.</span><span class="sxs-lookup"><span data-stu-id="162fe-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="162fe-113">Чтобы переместить локального пользователя в клиент Lync Online, выполните в командной консоли Lync Server следующие командлеты с помощью учетных данных администратора для вашего клиента Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="162fe-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="162fe-114">Замените "username@contoso.com" на информацию о перемещаемом пользователе.</span><span class="sxs-lookup"><span data-stu-id="162fe-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```
    $creds=Get-Credential
   ```

   ```
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="162fe-115">Формат URL-адреса, заданный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, на котором запущена служба размещенной миграции, в следующем формате:\<HTTPS://FQDN\>Pool/хостедмигратион/ Хостедмигратионсервице. svc.</span><span class="sxs-lookup"><span data-stu-id="162fe-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="162fe-116">URL-адрес службы миграции с размещением можно определить по URL-адресу панели управления Lync Online для учетной записи клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="162fe-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="162fe-117">**Определение URL-адреса размещенной службы миграции для своего клиента Office 365**</span><span class="sxs-lookup"><span data-stu-id="162fe-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="162fe-118">Выполните вход в свое клиентское приложение Office 365 как администратор.</span><span class="sxs-lookup"><span data-stu-id="162fe-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="162fe-119">Откройте **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="162fe-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="162fe-120">В **центре администрирования Lync** выберите и скопируйте URL-адрес в адресной строке на **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="162fe-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="162fe-121">Ниже показан возможны пример URL-адреса</span><span class="sxs-lookup"><span data-stu-id="162fe-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="162fe-122">После замены фрагмента **webdir** в URL-адресе фрагментом **admin** получается следующий результат:</span><span class="sxs-lookup"><span data-stu-id="162fe-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="162fe-123">Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="162fe-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="162fe-124">Итоговый URL-адрес, который служит значением параметра **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="162fe-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="162fe-125">Перемещение пользователей в Lync Online</span><span class="sxs-lookup"><span data-stu-id="162fe-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="162fe-126">Вы можете переместить нескольких пользователей с помощью командлета [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) с параметром – Filter, чтобы выбрать пользователей с определенным свойством, назначенным учетным записям пользователей, например регистрарпул.</span><span class="sxs-lookup"><span data-stu-id="162fe-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="162fe-127">Затем можно передать возвращенные пользователи в командлет [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="162fe-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="162fe-128">Вы также можете использовать параметр –OU для получения всех пользователей в указанном подразделении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="162fe-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="162fe-129">Проверка параметров и функций пользователей Lync Online</span><span class="sxs-lookup"><span data-stu-id="162fe-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="162fe-130">Можно проверить успешность перемещения пользователя следующими способами:</span><span class="sxs-lookup"><span data-stu-id="162fe-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="162fe-131">Просмотр состояния пользователя на панели управления Lync Online.</span><span class="sxs-lookup"><span data-stu-id="162fe-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="162fe-132">Визуальный индикатор для локальных пользователей и пользователей в сети отличается.</span><span class="sxs-lookup"><span data-stu-id="162fe-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="162fe-133">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="162fe-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

