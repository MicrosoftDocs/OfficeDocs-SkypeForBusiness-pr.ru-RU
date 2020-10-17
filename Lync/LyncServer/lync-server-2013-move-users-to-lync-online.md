---
title: 'Lync Server 2013: перемещение пользователей в Lync Online'
description: 'Lync Server 2013: перемещение пользователей в Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 501eda3a76cec3226831c0af3631317377cd82cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541995"
---
# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="a4960-103">Перемещение пользователей в Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4960-103">Move users to Lync Online in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4960-104">_**Последнее изменение темы:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="a4960-104">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="a4960-105">Прежде чем приступить к переносу пользователей на Lync Online, необходимо создать резервную копию пользовательских данных, связанных с перемещаемыми учетными записями.</span><span class="sxs-lookup"><span data-stu-id="a4960-105">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="a4960-106">Не все данные пользователя перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4960-106">Not all user data is moved with the user account.</span></span> <span data-ttu-id="a4960-107">Дополнительные сведения приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="a4960-107">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="a4960-108">Перенос параметров пользователя в Lync Online</span><span class="sxs-lookup"><span data-stu-id="a4960-108">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="a4960-109">Параметры пользователя перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4960-109">User settings are moved with the user account.</span></span> <span data-ttu-id="a4960-110">Некоторые локальные параметры не перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="a4960-110">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="a4960-111">Перемещение пилотных пользователей в Lync Online</span><span class="sxs-lookup"><span data-stu-id="a4960-111">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="a4960-112">Прежде чем приступить к перемещению пользователей в Lync Online, вам может потребоваться переместить несколько пилотных пользователей, чтобы убедиться, что среда настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="a4960-112">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="a4960-113">После этого вы можете проверить, что функции и службы Lync работают должным образом, прежде чем пытаться переместить дополнительных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a4960-113">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="a4960-114">Чтобы переместить локального пользователя в клиент Lync Online, выполните следующие командлеты в командной консоли Lync Server, используя учетные данные администратора для своей организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4960-114">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="a4960-115">Замените "username@contoso.com" информацией для пользователя, которого требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="a4960-115">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="a4960-116">Формат URL-адреса, заданный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, где запущена служба переноса, в следующем формате: https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="a4960-116">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="a4960-117">Можно определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для учетной записи организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4960-117">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="a4960-118">**Определение URL-адреса размещенной службы миграции для Организации**</span><span class="sxs-lookup"><span data-stu-id="a4960-118">**To determine the Hosted Migration Service URL for your organization**</span></span>

1.  <span data-ttu-id="a4960-119">Войдите в организацию Microsoft 365 или Office 365 с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="a4960-119">Login to your Microsoft 365 or Office 365 organization as an administrator.</span></span>

2.  <span data-ttu-id="a4960-120">Откройте **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="a4960-120">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="a4960-121">При отображении **центра администрирования Lync** выберите и скопируйте URL-адрес в адресную строку вплоть до **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="a4960-121">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="a4960-122">Пример URL-адреса выглядит примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a4960-122">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="a4960-123">Замените **webdir** в URL-адресе на **"Администратор"**, что приводит к следующим действиям:</span><span class="sxs-lookup"><span data-stu-id="a4960-123">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="a4960-124">Добавьте указанную ниже строку в URL-адрес: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="a4960-124">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="a4960-125">Итоговый URL-адрес, который является значением **хостедмигратионоверридеурл**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a4960-125">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="a4960-126">Перемещение пользователей в Lync Online</span><span class="sxs-lookup"><span data-stu-id="a4960-126">Moving Users to Lync Online</span></span>

<span data-ttu-id="a4960-127">Можно переместить несколько пользователей с помощью командлета [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) с параметром – Filter, чтобы выбрать пользователей с определенным свойством, назначенным учетным записям пользователей, например RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="a4960-127">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="a4960-128">Затем можно передать возвращенных пользователей в командлет [Move – CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a4960-128">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="a4960-129">Вы также можете использовать параметр – OU для получения всех пользователей в указанном подразделении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a4960-129">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="a4960-130">Проверка пользовательских параметров и функций Lync Online</span><span class="sxs-lookup"><span data-stu-id="a4960-130">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="a4960-131">Можно проверить успешность перемещения пользователя следующими способами:</span><span class="sxs-lookup"><span data-stu-id="a4960-131">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="a4960-p107">просмотреть состояние пользователя в панели управления Lync Online: визуальные индикаторы для локальных и сетевых пользователей различаются;</span><span class="sxs-lookup"><span data-stu-id="a4960-p107">View the status of the user in the Lync Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="a4960-134">выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="a4960-134">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

