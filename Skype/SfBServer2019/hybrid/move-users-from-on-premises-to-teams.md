---
title: Перемещение пользователей из локальной группы
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Сводка: Узнайте, как перенос параметров пользователя и перемещение пользователей в группы.'
ms.openlocfilehash: 27e8ac831f7009a373b2ed28d484f00f9462ef12
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030786"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="ce3e6-103">Перемещение пользователей из локальной группы</span><span class="sxs-lookup"><span data-stu-id="ce3e6-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="ce3e6-104">Скайп Business Server 2019 можно выполнить миграцию локальных пользователей группам, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-104">With Skype for Business Server 2019, you can migrate your on-premises users to Teams as described in this article.</span></span>

<span data-ttu-id="ce3e6-105">Необходимо учитывать, после перемещения пользователей по группам:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-105">Be aware that after moving your users to Teams:</span></span> 
 
- <span data-ttu-id="ce3e6-106">Свои собрания перенесены на Скайп для бизнеса в Интернет и перенесены свои контакты по группам.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-106">Their meetings are migrated to Skype for Business Online, and their contacts are migrated to Teams.</span></span> 
- <span data-ttu-id="ce3e6-107">Они могут присоединиться к собраниям Скайп через Скайп для бизнеса Расширенный клиент (пользователи не запрос для входа в каждом) или с помощью приложения Скайп собрания (требуется одновременно загрузить и входа).</span><span class="sxs-lookup"><span data-stu-id="ce3e6-107">They can join Skype meetings through the Skype for Business rich client (users are not prompted for sign-in each time) or through the Skype Meetings App (requires a one-time download and sign-in).</span></span> <span data-ttu-id="ce3e6-108">Когда пользователь щелкает Скайп для бизнеса собрания ссылки внутри групп, в соответствующие приложения открывается собрания.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-108">When a user clicks on a Skype for Business meeting link within Teams, the meeting will launch in the appropriate app.</span></span>

- <span data-ttu-id="ce3e6-109">На мобильном устройстве, вашей пользователи смогут присоединиться к существующей Скайп для собраний бизнеса с помощью только встроенное приложение.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-109">On Mobile, your users will be able to join existing Skype for Business meetings using the native app only.</span></span>

    ![Скайп Mobile собрания](../media/mobile-skype-meeting.png)

> [!NOTE]
> <span data-ttu-id="ce3e6-111">После перемещения пользователя в режим TeamsOnly пользователя размещенный в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-111">After a user is moved to TeamsOnly mode, the user is homed in Skype for Business Online.</span></span>

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a><span data-ttu-id="ce3e6-112">Предварительные требования для перемещения локальных пользователей по группам</span><span class="sxs-lookup"><span data-stu-id="ce3e6-112">Prerequisites for moving on-premises users to Teams</span></span> 

<span data-ttu-id="ce3e6-113">В этом разделе описываются предварительные требования для перемещения локальных пользователей по группам.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-113">This section describes the prerequisites for moving your on-premises users to Teams.</span></span> <span data-ttu-id="ce3e6-114">Вы должны:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-114">You must:</span></span>
- <span data-ttu-id="ce3e6-115">[Настройка гибридного подключения](#set-up-hybrid-connectivity) (если еще не сделано)</span><span class="sxs-lookup"><span data-stu-id="ce3e6-115">[Set up hybrid connectivity](#set-up-hybrid-connectivity) (if you have not already done so)</span></span>
- <span data-ttu-id="ce3e6-116">[Уведомления пользователей о переход на группы](#notify-your-users-of-the-move-to-teams) (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ce3e6-116">[Notify your users of the move to Teams](#notify-your-users-of-the-move-to-teams) (optional)</span></span>
- [<span data-ttu-id="ce3e6-117">Убедитесь, что пользователи имеют лицензию</span><span class="sxs-lookup"><span data-stu-id="ce3e6-117">Ensure that your users have a valid license</span></span>](#make-sure-your-users-have-a-valid-license)
- [<span data-ttu-id="ce3e6-118">Необходимо учитывать требования к конфигурации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ce3e6-118">Be aware of voice configuration requirements</span></span>](#voice-configuration-requirements)
- <span data-ttu-id="ce3e6-119">[Назначение политики обновление группы](#assign-a-teams-upgrade-policy) (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ce3e6-119">[Assign a Teams Upgrade policy](#assign-a-teams-upgrade-policy) (optional)</span></span>

## <a name="set-up-hybrid-connectivity"></a><span data-ttu-id="ce3e6-120">Настройка гибридного подключения</span><span class="sxs-lookup"><span data-stu-id="ce3e6-120">Set up hybrid connectivity</span></span>
<span data-ttu-id="ce3e6-121">Перед миграцией пользователей, если это еще не сделано, следует убедиться, что вы настроили гибридного подключения между Скайп для локальной среды Business Server и Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-121">Before you migrate your users, if you have not already done so, you must ensure that you have configured hybrid connectivity between your Skype for Business Server on-premises environment and Skype for Business Online.</span></span> <span data-ttu-id="ce3e6-122">Гибридного подключения требует синхронизации Active Directory, настройки федерации и т. д.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-122">Hybrid connectivity requires Active Directory synchronization, configuring federation, and so on.</span></span> <span data-ttu-id="ce3e6-123">Дополнительные сведения см в [планировании гибридного подключения](plan-hybrid-connectivity.md) и [Настройка гибридного подключения](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="ce3e6-123">For more information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

## <a name="notify-your-users-of-the-move-to-teams"></a><span data-ttu-id="ce3e6-124">Уведомления пользователей о переход на группы</span><span class="sxs-lookup"><span data-stu-id="ce3e6-124">Notify your users of the move to Teams</span></span> 
<span data-ttu-id="ce3e6-125">Это необязательный этап, кроме одного, которое следует учесть.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-125">This is an optional step, but one that you should consider.</span></span> <span data-ttu-id="ce3e6-126">Для уведомления пользователей о ожидающие обновления группы, можно использовать командлеты TeamsUpgradePolicy и TeamsUpgradeConfiguration локальных.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-126">To notify users of the pending Teams upgrade, you can use the on-premises TeamsUpgradePolicy and TeamsUpgradeConfiguration cmdlets.</span></span> <span data-ttu-id="ce3e6-127">Можно также настроить автоматической auto-файл для загрузки групп в фоновом режиме перед обновлением (только для клиентов Win32).</span><span class="sxs-lookup"><span data-stu-id="ce3e6-127">You can also configure silent auto-download of Teams in the background prior to upgrade (Win32 clients only).</span></span> 

<span data-ttu-id="ce3e6-128">Например уведомляющие пользователей, что они обновляемые группам, командлет локальной TeamsUpgradePolicy совместно с параметром - NotifySbUser.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-128">For example, to notify users that they are being upgraded to Teams, use the on-premises TeamsUpgradePolicy cmdlet with the -NotifySbUser parameter.</span></span> <span data-ttu-id="ce3e6-129">Можно задать политику глобальная, уровня сайта, пул или пользователя.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-129">You can set the policy on a global, site, pool, or user level.</span></span> <span data-ttu-id="ce3e6-130">Следующая команда создает и предоставляет политику уровня пользователя:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-130">The following command creates and grants a user-level policy:</span></span>
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

<span data-ttu-id="ce3e6-131">Вы можете проверить эту политику с помощью командлета Get-csTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-131">You can check this policy by using the Get-csTeamsUpgradePolicy cmdlet.</span></span>

<span data-ttu-id="ce3e6-132">Пользователи увидят уведомление о предстоящих перемещения по группам.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-132">Your users will see a notification of the impending move to Teams.</span></span> <span data-ttu-id="ce3e6-133">Уведомление происходит на Win32, Mac, мобильных устройств и веб-клиентов (с правом версия).</span><span class="sxs-lookup"><span data-stu-id="ce3e6-133">The notification occurs on Win32, Mac, Mobile, and Web Clients (with the right version).</span></span>

<span data-ttu-id="ce3e6-134">Можно указать автоматической загрузки рабочих групп (для клиентов Win32) для пользователей обновляется с использованием командлета TeamsUpgradeConfiguration локальной совместно с параметром DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-134">You can specify automatic download of Teams (for Win32 clients) for users being upgraded by using the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="ce3e6-135">Эта политика установлена на уровне клиента, и он может применяться для глобальной, сайта и уровне пула.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-135">You set this policy at the tenant level, and it can be applied on a global, site, and pool level.</span></span> <span data-ttu-id="ce3e6-136">Например следующая команда задает политику на уровне сайта:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-136">For example, the following command sets the policy at the site level:</span></span>

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

<span data-ttu-id="ce3e6-137">По умолчанию значение DownloadTeams имеет значение True, но необходимо также установить NotifySfbUser имеет значение True для включения групп для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-137">By default, the value of DownloadTeams is True, but you must also set NotifySfbUser to True to enable Teams for a given user.</span></span> 

## <a name="make-sure-your-users-have-a-valid-license"></a><span data-ttu-id="ce3e6-138">Убедитесь в том, что пользователи имеют лицензию</span><span class="sxs-lookup"><span data-stu-id="ce3e6-138">Make sure your users have a valid license</span></span>  
<span data-ttu-id="ce3e6-139">Перед выполнением переноса локального пользователя должно быть задано действительная лицензия следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-139">Before migration, the on-premises user must be given a valid license, as follows:</span></span>

-   <span data-ttu-id="ce3e6-140">Пользователь должен иметь лицензию группами.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-140">User must have a Teams license.</span></span>
-   <span data-ttu-id="ce3e6-141">Если пользователь настроен для использования локальной корпоративной голосовой связи, они должны иметь лицензию на сетевой голосовой при перемещении.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-141">If the user is configured to use on-premises Enterprise Voice, they must have an online voice license when moving.</span></span> 
-   <span data-ttu-id="ce3e6-142">Если пользователь настроена для локальной телефонных конференций, они должны иметь лицензию для телефонной системой (облако УАТС).</span><span class="sxs-lookup"><span data-stu-id="ce3e6-142">If the user is configured for on-premises dial-in conferencing, they must have a license for Phone System (Cloud PBX).</span></span>

## <a name="voice-configuration-requirements"></a><span data-ttu-id="ce3e6-143">Требования к конфигурации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ce3e6-143">Voice configuration requirements</span></span>

<span data-ttu-id="ce3e6-144">Если локальных пользователей локальной голосовой связи, у вас есть два варианта:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-144">If your on-premises users have on-premises voice, you have two options:</span></span>

-  <span data-ttu-id="ce3e6-145">**Перенос пользователей с помощью функции телефонии.**</span><span class="sxs-lookup"><span data-stu-id="ce3e6-145">**Migrate users with telephony capabilities.**</span></span> <span data-ttu-id="ce3e6-146">Пользователи могут выполнение и прием звонков с помощью команды клиента.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-146">Users can make and receive calls using the Teams client.</span></span>  <span data-ttu-id="ce3e6-147">Вы можете вызов планирование Microsoft или прямой маршрутизации для подключения к группам служб телефонии.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-147">You can choose either Microsoft Calling Plan or Direct Routing to connect the telephony services to Teams.</span></span>  

    -  <span data-ttu-id="ce3e6-148">Вызов планирование Майкрософт предоставляет решение все-в--облачной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-148">Microsoft Calling Plan provides an all-in-the-cloud voice solution.</span></span> <span data-ttu-id="ce3e6-149">Дополнительные сведения о вызове планирование Microsoft ссылка (готовится к выпуску).</span><span class="sxs-lookup"><span data-stu-id="ce3e6-149">For more information about Microsoft Calling Plan, see (link coming soon).</span></span> 
    -  <span data-ttu-id="ce3e6-150">Прямое маршрутизации позволяет использовать практически любого магистрали ТСОП и можно настроить взаимодействие между владении клиента телефонное оборудование и телефонной системой Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-150">Direct Routing lets you use virtually any PSTN trunk,  and you can configure interoperability between customer-owned telephony equipment and Microsoft Phone System.</span></span>  <span data-ttu-id="ce3e6-151">Для получения дополнительных сведений см [Планирование прямого](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) и [Настроить прямое маршрутизации](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="ce3e6-151">For more information, see [Plan Direct Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) and [Configure Direct Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).</span></span>

-  <span data-ttu-id="ce3e6-152">**Перенос пользователей без возможности телефонной связи.**</span><span class="sxs-lookup"><span data-stu-id="ce3e6-152">**Migrate users without telephony capabilities.**</span></span> <span data-ttu-id="ce3e6-153">Если производится перенос пользователей без сохранения функции телефонии, убедитесь, что пользователи имеют соответствующие лицензий в облаке.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-153">If you migrate users without preserving  telephony capabilities, make sure users have appropriate licenses in the cloud.</span></span> 

## <a name="assign-a-teams-upgrade-policy"></a><span data-ttu-id="ce3e6-154">Назначение политики обновление группы</span><span class="sxs-lookup"><span data-stu-id="ce3e6-154">Assign a Teams Upgrade policy</span></span>  
<span data-ttu-id="ce3e6-155">Online средства можно использовать для управления политиками пользователя, например, для управления маршрутизацией входящих сообщений и звонки.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-155">You can use online tools to manage user policies, such as to control routing of incoming messages and calls.</span></span> <span data-ttu-id="ce3e6-156">Для получения дополнительных сведений см (готовится к выпуску).</span><span class="sxs-lookup"><span data-stu-id="ce3e6-156">For more information, see (link coming soon).</span></span>

## <a name="move-on-premises-users-to-teams"></a><span data-ttu-id="ce3e6-157">Перемещение пользователей в локальной группы</span><span class="sxs-lookup"><span data-stu-id="ce3e6-157">Move on-premises users to Teams</span></span>

<span data-ttu-id="ce3e6-158">Можно переместить локальных пользователей в группы, с помощью командлетов PowerShell или с помощью Скайп для панели управления 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-158">You can move your on-premises users to Teams by using PowerShell cmdlets or by using the Skype for Business Server 2019 Control Panel.</span></span>

### <a name="move-users-by-using-powershell"></a><span data-ttu-id="ce3e6-159">Перемещение пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce3e6-159">Move users by using PowerShell</span></span>
<span data-ttu-id="ce3e6-160">Для перемещения пользователей в группы с помощью PowerShell, вы будете использовать командлета Move-CsUser с параметром moveToTeams следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-160">To move your users to Teams by using PowerShell, you’ll use the Move-CsUser cmdlet with the moveToTeams parameter as follows:</span></span>

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

<span data-ttu-id="ce3e6-161">($cred = get-учетные данные.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-161">($cred = get-Credentials.</span></span> <span data-ttu-id="ce3e6-162">Необходимо предоставить учетные данные администратора Office 365.)</span><span class="sxs-lookup"><span data-stu-id="ce3e6-162">You must provide Office 365 admin credentials.)</span></span>

> [!NOTE]
> <span data-ttu-id="ce3e6-163">Эта команда показана TeamsInteropPolicy групп и TeamsUpgradePolicy на TeamsOnly режим.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-163">This command sets the TeamsInteropPolicy to Teams and sets the TeamsUpgradePolicy to TeamsOnly mode.</span></span> 
 
<span data-ttu-id="ce3e6-164">После успешного завершения перемещения по группам, Скайп пользователя для клиента Business будет отображаться следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-164">After the move to Teams is successful, the user’s Skype for Business client will display the following message:</span></span> 

![Выполнена успешно миграции для группы сообщений](../media/teams-upgrade-complete-message.png)

<span data-ttu-id="ce3e6-166">Обратите внимание на то, что Скайп для бизнеса больше не будет доступен пользователю, за исключением Чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-166">Note that Skype for Business will no longer be available to the user except to join a meeting.</span></span> 

<span data-ttu-id="ce3e6-167">В редких случаях при переносе пользователей в группы можно переопределить телефонных конференций и облачных функций голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-167">In rare cases, when moving your users to Teams, you might want to override dial-in conferencing and cloud voice functionality.</span></span> <span data-ttu-id="ce3e6-168">Это можно сделать с помощью следующих параметров с помощью команды Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-168">You can do this by using the following parameters with the Move-CsUser command:</span></span>
- <span data-ttu-id="ce3e6-169">**BypassAudioConferencingCheck:** Если пользователь имеет телефонных конференций включен для локальных, пользователь также должен иметь лицензию AudioConf, назначенные в Office 365 перед миграцией.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-169">**BypassAudioConferencingCheck:** If a user has dial-in conferencing enabled for on-premises, the user must also have an AudioConf license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="ce3e6-170">После миграции в облако, пользователь будет выполнена подготовка для аудиоконференций в облаке.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-170">Once migrated to the cloud, the user will be provisioned for audio conferencing in the cloud.</span></span> <span data-ttu-id="ce3e6-171">Если для какой-либо причине, необходимо переместить пользователя в облаке, но не использовать функциональные возможности аудиоконференций, его можно переопределить, если указать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-171">If, for some reason, you want to move a user to the cloud, but not use the audio conferencing functionality, you can override it by specifying this parameter.</span></span>
- <span data-ttu-id="ce3e6-172">**ByPassEnterpriseVoice:** Если пользователь имеет включен для локальной корпоративной голосовой связи, пользователь должен иметь лицензию корпоративной голосовой связи, назначенные в Office 365 перед миграцией.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-172">**ByPassEnterpriseVoice:** If a user has Enterprise Voice enabled for on-premises, the user must have an Enterprise Voice license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="ce3e6-173">После миграции в облако пользователь будет выполнена подготовка для голосовой связи в облаке.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-173">After migration to the cloud, the user will be provisioned for voice in the cloud.</span></span> <span data-ttu-id="ce3e6-174">Если для какой-либо причине, необходимо переместить пользователя в облаке, но не использовать функциональные возможности голосовой связи облако, облако голосовой связи можно переопределить, указав этот параметр.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-174">If, for some reason, you want to move a user to the cloud but not use cloud voice functionality, you can override cloud voice by specifying this parameter.</span></span>
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="ce3e6-175">Перемещение пользователей с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="ce3e6-175">Move users by using the Skype for Business Server Control Panel</span></span> 

<span data-ttu-id="ce3e6-176">Чтобы переместить пользователей в группы с помощью Скайп для панели управления бизнеса:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-176">To move users to Teams by using the Skype for Business Control Panel:</span></span>

1. <span data-ttu-id="ce3e6-177">Откройте Скайп для панели управления бизнеса и войдите в свою учетную запись Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-177">Open the Skype for Business Control Panel and sign in to your Office 365 account.</span></span>

2. <span data-ttu-id="ce3e6-178">Выберите **пользователей** в левой панели навигации и выберите пользователей для миграции.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-178">Select **Users** in the left navigation, and select the users to migrate.</span></span> 
     
3. <span data-ttu-id="ce3e6-179">В меню **Действие** выберите команду **переместить выбранных пользователей в группы**.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-179">On the **Action** menu, choose **Move selected users to Teams**.</span></span> 

    ![Нажмите кнопку Далее, чтобы подтвердить миграции](../media/migration-confirmation.png)
    
4. <span data-ttu-id="ce3e6-181">Нажмите кнопку **Далее** для подтверждения миграции.</span><span class="sxs-lookup"><span data-stu-id="ce3e6-181">Click **Next** to confirm your migration.</span></span> 

<span data-ttu-id="ce3e6-182">После перемещения пользователей в группы можно увидеть подтверждений следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-182">After the user is moved to Teams, you will see  confirmations like the following:</span></span>

<span data-ttu-id="ce3e6-183">![Перемещение пользователей подтверждения](../media/move-user-confirmation.png)
</span><span class="sxs-lookup"><span data-stu-id="ce3e6-183">![Move users confirmation](../media/move-user-confirmation.png)
</span></span><br/><br/>
<span data-ttu-id="ce3e6-184">![Сообщение, что пользователи были перемещены](../media/users-moved-successfully.png)</span><span class="sxs-lookup"><span data-stu-id="ce3e6-184">![Message that users have been moved](../media/users-moved-successfully.png)</span></span>

<span data-ttu-id="ce3e6-185">Если не удалось выполнить move, появится сообщение следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ce3e6-185">If the move was not successful, you will see a message like the following:</span></span>

![Сообщение, которое не удалось переместить пользователя](../media/users-not-moved.png)