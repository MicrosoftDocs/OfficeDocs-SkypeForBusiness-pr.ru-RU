---
title: 'Lync Server 2013: перемещение пользователей в Lync Online'
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
ms.openlocfilehash: f39f28a2a642a30621e7fd3fd9d8a1beea9a4e14
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="c98de-102">Перемещение пользователей в Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c98de-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c98de-103">_**Последнее изменение темы:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="c98de-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="c98de-104">Прежде чем приступить к переносу пользователей на Lync Online, необходимо создать резервную копию пользовательских данных, связанных с перемещаемыми учетными записями.</span><span class="sxs-lookup"><span data-stu-id="c98de-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="c98de-105">Не все данные пользователя перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="c98de-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="c98de-106">Дополнительные сведения приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="c98de-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="c98de-107">Перенос параметров пользователя в Lync Online</span><span class="sxs-lookup"><span data-stu-id="c98de-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="c98de-108">Параметры пользователя перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="c98de-108">User settings are moved with the user account.</span></span> <span data-ttu-id="c98de-109">Некоторые локальные параметры не перемещаются вместе с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="c98de-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="c98de-110">Перемещение пилотных пользователей в Lync Online</span><span class="sxs-lookup"><span data-stu-id="c98de-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="c98de-111">Прежде чем приступить к перемещению пользователей в Lync Online, вам может потребоваться переместить несколько пилотных пользователей, чтобы убедиться, что среда настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="c98de-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="c98de-112">После этого вы можете проверить, что функции и службы Lync работают должным образом, прежде чем пытаться переместить дополнительных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c98de-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="c98de-113">Чтобы переместить локального пользователя в клиент Lync Online, выполните следующие командлеты в командной консоли Lync Server, используя учетные данные администратора для клиента Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="c98de-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="c98de-114">Замените "username@contoso.com" информацией для пользователя, которого требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="c98de-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="c98de-115">Формат URL-адреса, указанный для параметра **хостедмигратионоверридеурл** , должен быть URL-адресом пула, где запущена служба переноса, в следующем формате: https://\<Pool FQDN/HostedMigration/hostedmigrationService.svc.\></span><span class="sxs-lookup"><span data-stu-id="c98de-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="c98de-116">Вы можете определить URL-адрес размещенной службы миграции, просмотрев URL-адрес панели управления Lync Online для своей учетной записи клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="c98de-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="c98de-117">**Определение размещенного URL-адреса службы миграции для клиента Office 365**</span><span class="sxs-lookup"><span data-stu-id="c98de-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="c98de-118">Войдите в свой клиент Office 365 от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="c98de-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="c98de-119">Откройте **центр администрирования Lync**.</span><span class="sxs-lookup"><span data-stu-id="c98de-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="c98de-120">При отображении **центра администрирования Lync** выберите и скопируйте URL-адрес в адресную строку вплоть до **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="c98de-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="c98de-121">Пример URL-адреса выглядит примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c98de-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="c98de-122">Замените **webdir** в URL-адресе на **"Администратор"**, что приводит к следующим действиям:</span><span class="sxs-lookup"><span data-stu-id="c98de-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="c98de-123">Добавьте указанную ниже строку в URL-адрес: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="c98de-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="c98de-124">Итоговый URL-адрес, который является значением **хостедмигратионоверридеурл**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c98de-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="c98de-125">Перемещение пользователей в Lync Online</span><span class="sxs-lookup"><span data-stu-id="c98de-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="c98de-126">Можно переместить несколько пользователей с помощью командлета [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) с параметром – Filter, чтобы выбрать пользователей с определенным свойством, назначенным учетным записям пользователей, например RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="c98de-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="c98de-127">Затем можно передать возвращенных пользователей в командлет [Move – CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c98de-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="c98de-128">Вы также можете использовать параметр – OU для получения всех пользователей в указанном подразделении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c98de-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="c98de-129">Проверка пользовательских параметров и функций Lync Online</span><span class="sxs-lookup"><span data-stu-id="c98de-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="c98de-130">Можно проверить успешность перемещения пользователя следующими способами:</span><span class="sxs-lookup"><span data-stu-id="c98de-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="c98de-p107">просмотреть состояние пользователя в панели управления Lync Online: визуальные индикаторы для локальных и сетевых пользователей различаются;</span><span class="sxs-lookup"><span data-stu-id="c98de-p107">View the status of the user in the Lync Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="c98de-133">выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c98de-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

