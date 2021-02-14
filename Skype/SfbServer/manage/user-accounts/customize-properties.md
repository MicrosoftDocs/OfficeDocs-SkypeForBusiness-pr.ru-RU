---
title: Настройка свойств учетной записи пользователя для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Для изменения свойств учетной записи отдельного пользователя можно использовать процедуры, которые используются в этом разделе.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826269"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="4f0e7-103">Настройка свойств учетной записи пользователя для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4f0e7-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="4f0e7-104">Для изменения свойств учетной записи отдельного пользователя можно использовать процедуры, которые используются в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="4f0e7-105">Существует две основные операции, которые можно сделать на уровне отдельного пользователя:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="4f0e7-106">Настройка параметров телефонии для определенной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="4f0e7-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="4f0e7-107">Перемещение пользователей в другой пул</span><span class="sxs-lookup"><span data-stu-id="4f0e7-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="4f0e7-108">Настройка параметров телефонии для определенной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="4f0e7-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="4f0e7-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="4f0e7-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="4f0e7-110">Вы можете настроить параметры телефонии для определенного пользователя (если для отдельного пользователя включена поддержка Skype для бизнеса Server и организация поддерживает телефонию).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="4f0e7-111">Ниже параметров телефонии пользователей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="4f0e7-112">**Отключено аудио- и видеосвязь** Пользователь не может звонить со звуком и видео.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="4f0e7-113">**Только с ПК на ПК** Пользователь может делать только аудио- или видеозвук с компьютера на компьютер.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="4f0e7-114">**Корпоративная голосовая связь** Пользователь может использовать инфраструктуру Skype для бизнеса Server для маршрутки всех входящих и исходяющих вызовов.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="4f0e7-115">Пользователь также может выполнять вызовы с компьютера на компьютер.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="4f0e7-116">**Удаленное управление звонками** Пользователь может управлять настольным телефоном с помощью Skype для бизнеса Server, а также звонить с компьютера на компьютер.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="4f0e7-117">Дополнительные сведения о настройке телефонии для организации см. в документации по развертыванию Корпоративная голосовая связь в Skype для бизнеса [Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) и развертывании Корпоративная голосовая связь в Skype для бизнеса [Server.](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)</span><span class="sxs-lookup"><span data-stu-id="4f0e7-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="4f0e7-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f0e7-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4f0e7-120">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4f0e7-121">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, которая требуется, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4f0e7-122">В таблице щелкните учетную запись пользователя, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="4f0e7-123">В меню **Правка** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="4f0e7-124">В разделе **Телефония** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="4f0e7-125">Чтобы отключить аудио- и видеовызовы для пользователя, щелкните **Аудио/видео отключено**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="4f0e7-p102">Чтобы включить аудиосвязь с компьютера на компьютер для пользователя, но при этом не включать удаленное управление вызовами или корпоративную голосовую связь, щелкните **Только с ПК на ПК**. Укажите значение для идентификатора **Линейный URI** для телефона, который пользователь использует для выполнения аудиовызовов с компьютера на компьютер.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="4f0e7-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="4f0e7-129">В поле **Линейный URI** укажите номер телефона для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="4f0e7-130">В полях **Политика абонентских групп** и **Политика голосовой связи** укажите соответствующие политики для пользователя.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="4f0e7-131">Чтобы указать правила нормализации для преобразования номеров телефона, набираемых пользователем, в формат E.164, выберите соответствующий профиль местоположения в разделе **Политика определения местоположения**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="4f0e7-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="4f0e7-133">В поле **Линейный URI** укажите номер телефона для удаленного управления вызовами.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="4f0e7-134">Для маршрутизации вызовов пользователю требуется настольный телефон и подключение к системе PBX.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="4f0e7-135">Перемещение пользователей в другой пул</span><span class="sxs-lookup"><span data-stu-id="4f0e7-135">Move users to another pool</span></span>
<span data-ttu-id="4f0e7-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="4f0e7-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="4f0e7-137">Панель управления Skype для бизнеса Server можно использовать для назначения пользователей определенному серверу или пулу.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="4f0e7-138">Перемещение всех существующих пользователей из пула источника, в который запущен Lync Server 2010 или более ранних этапов, в пул назначения Skype для бизнеса Server в сложной среде Active Directory может привести к замедлению репликации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="4f0e7-139">Чтобы избежать этого, можно использовать фильтры поиска для перемещения пользователей из пулов, в которые запущен Lync Server 2010 или более ранних серверов, отдельно или с помощью skype для бизнеса Server Management Shell для перемещения пользователей с помощью cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="4f0e7-140">Кроме того, функция фильтрации работает с пользователями Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="4f0e7-141">Перемещение выбранных пользователей на другой сервер или в другой пул</span><span class="sxs-lookup"><span data-stu-id="4f0e7-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="4f0e7-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f0e7-143">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4f0e7-144">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4f0e7-145">В поле **Search users** (Поиск пользователей) полностью или частично введите полное имя, отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности,  SIP-адрес или универсальный код ресурса (URI) требуемой учетной записи пользователя, а затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="4f0e7-146">В списке таблицы выберите одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="4f0e7-147">В меню **Actions** (Действия) щелкните пункт **Move selected users to pool** (Переместить выбранных пользователей в пул).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="4f0e7-148">В поле **Destination registrar pool** (Конечный пул регистратора) окна **Move Users** (Перемещение пользователей) выберите пул, в который необходимо переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="4f0e7-149">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** (Принудительно).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="4f0e7-p106">Если вы устанавливаете флажок **Force** (Принудительно), учетная запись пользователя перемещается, но при этом удаляются все связанные пользовательские данные (например, конференции, запланированные пользователем). Если вы не устанавливаете флажок, то перемещаются как связанные данные, так и сама учетная запись.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-p106">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="4f0e7-152">Перемещение всех пользователей из одного сервера или пула на другой сервер или в другой пул</span><span class="sxs-lookup"><span data-stu-id="4f0e7-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="4f0e7-153">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f0e7-154">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4f0e7-155">В левой панели навигации щелкните элемент **Users** (Пользователи).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4f0e7-156">В меню **Actions** (Действия) щелкните пункт **Move all users to pool** (Переместить всех пользователей в пул).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="4f0e7-157">В поле **Source registrar pool** (Исходный пул регистратора) окна **Move Users** (Перемещение пользователей) выберите пул, содержащий учетные записи пользователей, которые необходимо переместить.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="4f0e7-158">В поле **Destination registrar pool** (Конечный пул регистратора), выберите пул, в который необходимо переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="4f0e7-159">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** (Принудительно).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="4f0e7-p107">Если вы устанавливаете флажок **Force** (Принудительно), учетная запись пользователя перемещается, но при этом удаляются все связанные пользовательские данные (например, конференции, запланированные пользователем). Если вы не устанавливаете флажок, то перемещаются как связанные данные, так и сама учетная запись.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-p107">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="4f0e7-162">Перемещение пользователей из одного пула в другой пул с использованием фильтра</span><span class="sxs-lookup"><span data-stu-id="4f0e7-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="4f0e7-163">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f0e7-164">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4f0e7-165">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4f0e7-166">В **области поиска пользователей** **щелкните "Поиск"** и выберите **"Добавить фильтр".**</span><span class="sxs-lookup"><span data-stu-id="4f0e7-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="4f0e7-167">В области условий поиска выберите **Registrar Pool** (Пул регистратора), **Equal to** (Равно), **Current Pool FQDN** (Текущее полное доменное имя пула) и затем нажмите кнопку **Find** (Найти).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="4f0e7-168">В меню **Actions** (Действия) щелкните пункт **Move all users to pool** (Переместить всех пользователей в пул).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f0e7-169">После применения фильтра к существующему набору пользователей параметр **Move all users to pool** (Переместить всех пользователей в пул) действует в контексте отфильтрованного подмножества пользователей, а не для **всех** возможных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="4f0e7-170">В поле **Source registrar pool** (Исходный пул регистратора) окна **Move Users** (Перемещение пользователей) выберите пул, содержащий учетные записи пользователей, которые необходимо переместить.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="4f0e7-171">В поле **Destination registrar pool** (Конечный пул регистратора), выберите пул, в который необходимо переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="4f0e7-172">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** (Принудительно).</span><span class="sxs-lookup"><span data-stu-id="4f0e7-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="4f0e7-p108">Если вы устанавливаете флажок **Force** (Принудительно), учетная запись пользователя перемещается, но при этом удаляются все связанные пользовательские данные (например, конференции, запланированные пользователем, и контакты). Если вы не устанавливаете флажок, то перемещаются как связанные данные, так и сама учетная запись.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-p108">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="4f0e7-175">Перемещение пользователей из одного пула в другой с помощью windows Powershell</span><span class="sxs-lookup"><span data-stu-id="4f0e7-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="4f0e7-176">В зависимости от того, как вы Windows PowerShell команды (локально или удаленно), необходимо войти в систему в качестве члена правильных административных ролей Skype для бизнеса Server следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="4f0e7-177">а.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-177">a.</span></span> <span data-ttu-id="4f0e7-178">При запуске команд на локальном компьютере (например, вход непосредственно на сервер переднего интерфейса): войдите на компьютер, на котором установлена командная оболочка Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в описании разрешений делегирования **установки.**</span><span class="sxs-lookup"><span data-stu-id="4f0e7-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="4f0e7-179">б.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-179">b.</span></span> <span data-ttu-id="4f0e7-180">При удаленном запуске команд на другом компьютере (например, вход на компьютер и удаленный запуск команд на сервере переднего плана Standard Edition): из учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4f0e7-181">Запустите оболочку управления Skype для бизнеса Server: нажмите "Начните", выберите "Все программы",  **"Skype** для бизнеса" и "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="4f0e7-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4f0e7-182">Для перемещения отдельных пользователей используйте командлет Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="4f0e7-183">Здесь пользователь Pilar Ackerman перемещается из назначенного в данный момент домашнего пула в пул pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="4f0e7-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="4f0e7-184">Для перемещения большого числа пользователей используйте фильтры совместно с командлетом **Get-CsUser** и передавайте полученный набор пользователей в командлет **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="4f0e7-185">Совмещение команд **Get-CsUser** и **Move-CsUser** может дать следующий результат:</span><span class="sxs-lookup"><span data-stu-id="4f0e7-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


