---
title: Настройка свойств учетной записи пользователя в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Процедуры, описанные в этом разделе, можно использовать для изменения свойств учетной записи отдельных пользователей.
ms.openlocfilehash: eca88717d0b81ddd7c27fc140df9bdbf7590c5c6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991434"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="cedf0-103">Настройка свойств учетной записи пользователя в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cedf0-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="cedf0-104">Процедуры, описанные в этом разделе, можно использовать для изменения свойств учетной записи отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="cedf0-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="cedf0-105">Существует две основные операции, которые можно выполнить на уровне отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="cedf0-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="cedf0-106">Настройка параметров телефонии для определенной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="cedf0-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="cedf0-107">Перемещение пользователей в другой пул</span><span class="sxs-lookup"><span data-stu-id="cedf0-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="cedf0-108">Настройка параметров телефонии для определенной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="cedf0-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="cedf0-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="cedf0-109"></span></span>

<span data-ttu-id="cedf0-110">Вы можете настроить параметры телефонии для определенного пользователя (если для этого пользователя разрешено использовать Skype для бизнеса Server и организация поддерживает телефонную связь).</span><span class="sxs-lookup"><span data-stu-id="cedf0-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="cedf0-111">Ниже указаны параметры телефонной связи для пользователей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cedf0-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="cedf0-112">**Звук и видео отключены** Пользователь не может звонить с помощью звукового и видеосигнала.</span><span class="sxs-lookup"><span data-stu-id="cedf0-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="cedf0-113">**Только для** ПК Пользователь может выполнять только голосовые и видеозвонки между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="cedf0-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="cedf0-114">**Корпоративная голосовая связь** Пользователь может использовать инфраструктуру сервера Skype для бизнеса, чтобы маршрутизировать все входящие и исходящие звонки.</span><span class="sxs-lookup"><span data-stu-id="cedf0-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="cedf0-115">Пользователь также может звонить между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="cedf0-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="cedf0-116">**Удаленное управление звонками** Пользователь может использовать Skype для бизнеса Server для управления настольным телефоном, а также совершать звонки с компьютера на компьютер.</span><span class="sxs-lookup"><span data-stu-id="cedf0-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="cedf0-117">Дополнительные сведения о настройке телефонии для организации можно найти в разделе [Включение пользователей корпоративной голосовой связи в Skype для бизнеса Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) и [Развертывание корпоративной голосовой связи в Skype для бизнеса Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="cedf0-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="cedf0-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cedf0-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cedf0-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cedf0-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cedf0-120">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="cedf0-121">В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, диспетчер учетных записей безопасности (SAM), имя учетной записи, адрес SIP или универсальный код ресурса (URI) нужной учетной записи пользователя, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="cedf0-122">В таблице выберите учетную запись пользователя, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="cedf0-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="cedf0-123">В меню **Правка** выберите команду **изменить**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="cedf0-124">В разделе **телефония**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cedf0-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="cedf0-125">Чтобы отключить голосовые и видеозвонки для пользователя, нажмите кнопку **звук и видео отключено**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="cedf0-126">Чтобы включить голосовую связь между компьютерами для пользователя, но не удаленное управление звонками или голосовой телефон, выберите вариант **только для**ПК.</span><span class="sxs-lookup"><span data-stu-id="cedf0-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="cedf0-127">Укажите значение **универсального кода ресурса (URI)** для телефона, который пользователь использует для голосовой связи между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="cedf0-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="cedf0-128">Чтобы перенаправить телефонные звонки пользователя с помощью инфраструктуры Skype для бизнеса в соответствии с классом политики обслуживания, включая голосовую связь между ПК и компьютером, выберите **Корпоративный голосовой**стандарт.</span><span class="sxs-lookup"><span data-stu-id="cedf0-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="cedf0-129">В **URI строки**укажите номер телефона для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cedf0-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="cedf0-130">В **политике** и стратегии **голосовой**связи укажите соответствующие политики для пользователя.</span><span class="sxs-lookup"><span data-stu-id="cedf0-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="cedf0-131">Чтобы задать правила нормализации для перевода телефонных номеров, набранных пользователем, в формат E. 164, выберите соответствующий профиль местоположения в разделе **Политика местоположений**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="cedf0-132">Чтобы включить удаленное управление звонками, позволяющее пользователям контролировать телефонную линию на рабочем столе в Skype для бизнеса Server, чтобы звонить между компьютерами и телефонными звонками, нажмите кнопку **Удаленное управление звонками**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="cedf0-133">В **URI строки**укажите номер телефона для удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="cedf0-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="cedf0-134">Для маршрутизации звонков пользователь должен иметь подключение к рабочему столу и телефонной линии обмена филиалами.</span><span class="sxs-lookup"><span data-stu-id="cedf0-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="cedf0-135">Перемещение пользователей в другой пул</span><span class="sxs-lookup"><span data-stu-id="cedf0-135">Move users to another pool</span></span>
<span data-ttu-id="cedf0-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="cedf0-136"></span></span>

<span data-ttu-id="cedf0-137">Вы можете назначить пользователей для определенного сервера или пула с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cedf0-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="cedf0-138">Перемещение всех существующих пользователей из исходного пула, на котором работает Lync Server 2010 или более ранней версии, в пул назначения сервера Skype для бизнеса в сложной среде Active Directory может привести к более медленной репликации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cedf0-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="cedf0-139">Чтобы избежать этого, вы можете использовать фильтры поиска для перемещения пользователей из пулов, использующих Lync Server 2010 или более ранней версии, или с помощью командной консоли Skype для бизнеса Server для перемещения пользователей с помощью командлетов.</span><span class="sxs-lookup"><span data-stu-id="cedf0-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="cedf0-140">Кроме того, функция фильтрации работает для пользователей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cedf0-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="cedf0-141">Перемещение выбранных пользователей на другой сервер или в пул</span><span class="sxs-lookup"><span data-stu-id="cedf0-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="cedf0-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cedf0-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cedf0-143">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cedf0-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="cedf0-144">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="cedf0-145">В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, диспетчер учетных записей безопасности (SAM), имя учетной записи, адрес SIP или универсальный код ресурса (URI) нужной учетной записи пользователя, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="cedf0-146">В таблице выберите определенного пользователя или пользователей из списка.</span><span class="sxs-lookup"><span data-stu-id="cedf0-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="cedf0-147">В меню **действие** выберите пункт **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="cedf0-148">В разделе **Перемещение пользователей**выберите пул, в который вы хотите переместить пользователей, в **пул конечных регистраторов**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="cedf0-149">Необязательно Если целевой сервер или пул недоступны, установите флажок **принудительно** .</span><span class="sxs-lookup"><span data-stu-id="cedf0-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="cedf0-150">Если выбрать параметр **принудительно**, учетная запись пользователя будет перемещена, но все связанные с ней данные удаляются (например, Конференции, запланированные пользователем).</span><span class="sxs-lookup"><span data-stu-id="cedf0-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="cedf0-151">Если вы не выберете его, будет перемещена и учетная запись, и связанные данные.</span><span class="sxs-lookup"><span data-stu-id="cedf0-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="cedf0-152">Перемещение всех пользователей с одного сервера или пула на другой</span><span class="sxs-lookup"><span data-stu-id="cedf0-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="cedf0-153">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cedf0-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cedf0-154">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cedf0-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="cedf0-155">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="cedf0-156">В меню **действие** выберите пункт **переместить всех пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="cedf0-157">В разделе **Перемещение пользователей**выберите пул, содержащий учетные записи пользователей, которые вы хотите переместить в **пуле исходного регистратора**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="cedf0-158">В **пуле конечных регистраторов**выберите пул, на который вы хотите переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="cedf0-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="cedf0-159">Необязательно Если целевой сервер или пул недоступны, установите флажок **принудительно** .</span><span class="sxs-lookup"><span data-stu-id="cedf0-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="cedf0-160">Если выбрать параметр **принудительно**, учетная запись пользователя будет перемещена, но все связанные с ней данные удаляются (например, Конференции, запланированные пользователем).</span><span class="sxs-lookup"><span data-stu-id="cedf0-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="cedf0-161">Если вы не выберете его, будет перемещена и учетная запись, и связанные данные.</span><span class="sxs-lookup"><span data-stu-id="cedf0-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="cedf0-162">Перемещение пользователей из одного пула в другой с помощью фильтра</span><span class="sxs-lookup"><span data-stu-id="cedf0-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="cedf0-163">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cedf0-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cedf0-164">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cedf0-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cedf0-165">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="cedf0-166">В окне **Поиск пользователей**нажмите кнопку **Поиск**и выберите команду **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="cedf0-167">В условия поиска выберите пункт **пул регистраторов**, нажмите **кнопку равно**, выберите значение **Текущее полное доменное имя пула**и нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="cedf0-168">В меню **действие** выберите пункт **переместить всех пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cedf0-169">Если фильтр применяется к существующему набору пользователей, параметр **перемещает всех пользователей в пул** в контексте фильтрованного подмножества пользователей, а не **всех** возможных пользователей.</span><span class="sxs-lookup"><span data-stu-id="cedf0-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="cedf0-170">В разделе **Перемещение пользователей**выберите пул, содержащий учетные записи пользователей, которые вы хотите переместить в **пуле исходного регистратора**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="cedf0-171">В **пуле конечных регистраторов**выберите пул, куда вы хотите переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="cedf0-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="cedf0-172">Необязательно Если целевой сервер или пул недоступны, установите флажок **принудительно** .</span><span class="sxs-lookup"><span data-stu-id="cedf0-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="cedf0-173">Если выбрать параметр **принудительно**, учетная запись пользователя будет перемещена, но все связанные с ней данные удаляются (например, Конференции, запланированные пользователем, и контакты).</span><span class="sxs-lookup"><span data-stu-id="cedf0-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="cedf0-174">Если вы не выберете его, будет перемещена и учетная запись, и связанные данные.</span><span class="sxs-lookup"><span data-stu-id="cedf0-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="cedf0-175">Перемещение пользователей из одной группы в другую с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cedf0-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="cedf0-176">В зависимости от того, как выполняются команды Windows PowerShell (локальная или удаленная), вам нужно войти в систему в качестве участника подходящего административного роли сервера Skype для бизнеса, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="cedf0-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="cedf0-177">a)</span><span class="sxs-lookup"><span data-stu-id="cedf0-177">a.</span></span> <span data-ttu-id="cedf0-178">Если вы выполняете команды на локальном компьютере (например, входите на сервер переднего плана): Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами, описанными в разделе **Делегирование разрешений на настройку**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="cedf0-179">б)</span><span class="sxs-lookup"><span data-stu-id="cedf0-179">b.</span></span> <span data-ttu-id="cedf0-180">Если вы запускаете команды удаленно на другом компьютере (например, входите на компьютер и выполняете команды удаленно на стандартном внешнем сервере выпуска): от учетной записи пользователя, которой назначена роль Ксусерадминистратор или Ксадминистратор роль Войдите в систему на любом компьютере во внутренней среде.</span><span class="sxs-lookup"><span data-stu-id="cedf0-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cedf0-181">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Skype**для бизнеса и щелкните **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="cedf0-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="cedf0-182">Для перемещения отдельных пользователей используйте командлет Move-CsUser, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="cedf0-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="cedf0-183">Там, где пользователь может перемещаться — пользователь почтового Вронский, и пользователь перемещается из текущего назначенного домашнего пула в пул pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="cedf0-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="cedf0-184">Чтобы переместить большое количество пользователей, используйте фильтры с командлетом **Get-CsUser** и передавайте получившийся набор пользователей для перемещения. **CsUser**:</span><span class="sxs-lookup"><span data-stu-id="cedf0-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="cedf0-185">Объединенные команды **Get-CsUser** и **Move-CsUser** могут привести к следующим результатам:</span><span class="sxs-lookup"><span data-stu-id="cedf0-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


