---
title: Настройка свойств учетной записи пользователя для Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Для изменения свойств учетной записи отдельного пользователя, можно использовать процедуры, описанные в этом разделе.
ms.openlocfilehash: 5162cb187538b5288f13f25beae96f3775faa594
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214837"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="3a665-103">Настройка свойств учетной записи пользователя для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="3a665-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="3a665-104">Для изменения свойств учетной записи отдельного пользователя, можно использовать процедуры, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="3a665-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="3a665-105">Существует две основные операции, которые можно выполнить на уровне отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a665-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="3a665-106">Настройка параметров телефонии для конкретной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="3a665-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="3a665-107">Перемещение пользователей в другой пул</span><span class="sxs-lookup"><span data-stu-id="3a665-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="3a665-108">Настройка параметров телефонии для конкретной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="3a665-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="3a665-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="3a665-109"></span></span>

<span data-ttu-id="3a665-110">Можно настроить параметры телефонии для определенного пользователя (до тех пор отдельного пользователя включена поддержка Скайп для Business Server и телефонной связи поддерживает организации).</span><span class="sxs-lookup"><span data-stu-id="3a665-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="3a665-111">Скайп для параметры телефонии пользователей Business Server относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="3a665-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="3a665-112">**Этот параметр отключен аудио и видео** Пользователь не может выполнять вызовы с аудио- и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="3a665-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="3a665-113">**ПК только** Пользователь может выполнять только на ПК голосовые вызовы и видеовызовы.</span><span class="sxs-lookup"><span data-stu-id="3a665-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="3a665-114">**Корпоративная голосовая связь** Пользователя можно использовать Скайп для инфраструктуры Business Server для маршрутизации входящих и исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="3a665-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="3a665-115">Пользователь также может выполнять вызовы ПК-ПК.</span><span class="sxs-lookup"><span data-stu-id="3a665-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="3a665-116">**Удаленное управление звонками** Пользователь может использовать Скайп для Business Server для управления настольным телефоном и можно также выполнять вызовы ПК-ПК.</span><span class="sxs-lookup"><span data-stu-id="3a665-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="3a665-117">Для получения дополнительных сведений о настройке телефонии для организации содержатся в документации по развертыванию [Включить пользователей для корпоративной голосовой связи в Скайп для Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) и [Развертывание корпоративной голосовой связи в Скайп для Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) .</span><span class="sxs-lookup"><span data-stu-id="3a665-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="3a665-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3a665-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3a665-119">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a665-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3a665-120">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3a665-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3a665-121">В поле **поиска пользователей** , введите или первой части отображаемого имени, имени, последнего имя, имя учетной записи диспетчера учетных записей (SAM), SIP-адрес или строки универсальный код ресурса (URI) учетной записи пользователя и нажмите кнопку \*\*поиска \*\*.</span><span class="sxs-lookup"><span data-stu-id="3a665-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3a665-122">В таблице щелкните учетную запись пользователя, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="3a665-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="3a665-123">В меню **Правка** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="3a665-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="3a665-124">В разделе **Телефония**выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="3a665-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="3a665-125">Чтобы отключить аудио- и видеоконференций звонков для пользователя, щелкните **аудио/видео отключено**.</span><span class="sxs-lookup"><span data-stu-id="3a665-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="3a665-126">Чтобы включить для ПК звука коммуникаций для пользователя, но не удаленного управления звонками или корпоративной голосовой связи, щелкните **ПК-ПК только**.</span><span class="sxs-lookup"><span data-stu-id="3a665-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="3a665-127">Укажите значение для **URI линии** для телефона, который пользователь использует для коммуникаций звука на ПК.</span><span class="sxs-lookup"><span data-stu-id="3a665-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="3a665-128">Чтобы перенаправлять пользователя телефонные звонки с помощью Скайп для бизнес-инфраструктура в соответствии с классом политики службы, включая аудиосвязь ПК-ПК, щелкните **Корпоративной голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="3a665-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="3a665-129">В **Строке URI**укажите номер телефона для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3a665-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="3a665-130">В **Политика абонентской группы** и **политики голосовой связи**укажите соответствующие политики для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3a665-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="3a665-131">Чтобы задать правила нормализации для преобразования номеров телефонов набранный пользователем в формат E.164, выберите профиль соответствующее место в **политику расположения**.</span><span class="sxs-lookup"><span data-stu-id="3a665-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="3a665-132">Для включения удаленного вызова элемента управления, который позволяет пользователям управлять их настольных систем телефонной линии из Скайп для сервера для облегчения вызовы ПК-ПК и PC-to-phone вызовов, нажмите кнопку **удаленного управления звонками**.</span><span class="sxs-lookup"><span data-stu-id="3a665-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="3a665-133">В **Строке URI**укажите номер телефона для удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="3a665-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="3a665-134">Пользователь должен иметь стационарного телефона и относиться УАТС подключения для маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="3a665-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="3a665-135">Перемещение пользователей в другой пул</span><span class="sxs-lookup"><span data-stu-id="3a665-135">Move users to another pool</span></span>
<span data-ttu-id="3a665-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="3a665-136"></span></span>

<span data-ttu-id="3a665-137">Назначение пользователей для определенного сервера или пула, можно использовать Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a665-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="3a665-138">Перемещение всех существующих пользователей из пула источник, на котором работает Lync Server 2010 и более ранних версий Скайп для назначения пула Business Server сложных сред с Active Directory может привести к более медленных репликации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3a665-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="3a665-139">Чтобы избежать этого, фильтры поиска можно использовать для перемещения пользователей из пулов, работающих под управлением Lync Server 2010 или более ранних версий отдельно или Скайп для консоли Business Server можно использовать для переноса данных пользователей с помощью командлетов.</span><span class="sxs-lookup"><span data-stu-id="3a665-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="3a665-140">Кроме того функциональные возможности фильтрации работает с Скайп для пользователей Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a665-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="3a665-141">Чтобы переместить выбранных пользователей в другой сервер или в другой пул</span><span class="sxs-lookup"><span data-stu-id="3a665-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="3a665-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3a665-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3a665-143">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a665-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3a665-144">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3a665-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3a665-145">В поле **поиска пользователей** , введите или первой части отображаемого имени, имени, последнего имя, имя учетной записи диспетчера учетных записей (SAM), SIP-адрес или строки универсальный код ресурса (URI) учетной записи пользователя и нажмите кнопку \*\*поиска \*\*.</span><span class="sxs-lookup"><span data-stu-id="3a665-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="3a665-146">В таблице выберите одного или нескольких пользователей в списке.</span><span class="sxs-lookup"><span data-stu-id="3a665-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="3a665-147">В меню **Действие** выберите команду **переместить выбранных пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="3a665-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="3a665-148">В **Переместить пользователей**выберите пул, который необходимо переместить пользователей в **пул регистратора назначения**.</span><span class="sxs-lookup"><span data-stu-id="3a665-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="3a665-149">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** .</span><span class="sxs-lookup"><span data-stu-id="3a665-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3a665-150">Если выбран параметр **Force**, при перемещении учетной записи пользователя, но удаляется все данные пользователя (например, конференций, в которых пользователь запланировано).</span><span class="sxs-lookup"><span data-stu-id="3a665-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3a665-151">Если он не установлен, перемещаются учетную запись и связанных данных.</span><span class="sxs-lookup"><span data-stu-id="3a665-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="3a665-152">Для перемещения всех пользователей из одного сервера или пула на другой сервер или пул</span><span class="sxs-lookup"><span data-stu-id="3a665-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="3a665-153">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3a665-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3a665-154">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a665-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3a665-155">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3a665-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3a665-156">В меню **Действие** выберите команду **переместить всех пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="3a665-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="3a665-157">**Переместить пользователей**выберите пул, содержащий учетные записи пользователей, которые необходимо переместить в **исходный пул регистратора**.</span><span class="sxs-lookup"><span data-stu-id="3a665-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="3a665-158">В **конечном пуле регистратора**выберите пул, который требуется переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a665-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="3a665-159">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** .</span><span class="sxs-lookup"><span data-stu-id="3a665-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3a665-160">Если выбран параметр **Force**, при перемещении учетной записи пользователя, но удаляется все данные пользователя (например, конференций, в которых пользователь запланировано).</span><span class="sxs-lookup"><span data-stu-id="3a665-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3a665-161">Если он не установлен, перемещаются учетную запись и связанных данных.</span><span class="sxs-lookup"><span data-stu-id="3a665-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="3a665-162">Для перемещения пользователей из одного пула в другой пул с использованием фильтра</span><span class="sxs-lookup"><span data-stu-id="3a665-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="3a665-163">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3a665-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3a665-164">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a665-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3a665-165">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="3a665-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3a665-166">В **Поиск пользователей**нажмите кнопку **поиска**и нажмите кнопку **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="3a665-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="3a665-167">В области условий поиска выберите **Пул регистратора**, выберите **равно**, выберите **Текущее полное доменное имя пула**и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="3a665-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="3a665-168">В меню **Действие** выберите команду **переместить всех пользователей в пул**.</span><span class="sxs-lookup"><span data-stu-id="3a665-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a665-169">При применении фильтра на существующем наборе пользователей, параметр **переместить всех пользователей в пул** , находящийся в контексте отфильтрованное подмножество пользователей, не **все** возможные пользователями.</span><span class="sxs-lookup"><span data-stu-id="3a665-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="3a665-170">**Переместить пользователей**выберите пул, содержащий учетные записи пользователей, которые необходимо переместить в **исходный пул регистратора**.</span><span class="sxs-lookup"><span data-stu-id="3a665-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="3a665-171">В **конечный пул регистратора**выберите пул, где необходимо переместить пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a665-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="3a665-172">(Необязательно) Если конечный сервер или пул недоступен, установите флажок **Force** .</span><span class="sxs-lookup"><span data-stu-id="3a665-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3a665-173">Если выбран параметр **Force**, при перемещении учетной записи пользователя, но все данные пользователя удаляется (например, конференций, в которых пользователь запланированных и контакты).</span><span class="sxs-lookup"><span data-stu-id="3a665-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="3a665-174">Если он не установлен, перемещаются учетную запись и связанных данных.</span><span class="sxs-lookup"><span data-stu-id="3a665-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="3a665-175">Для перемещения пользователей из одного пула в другой с помощью командлетов Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="3a665-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="3a665-176">В зависимости от того, как вы выполняете команды Windows PowerShell (то есть локально или удаленно) необходимо выполнить вход в качестве члена правильных Скайп для административных ролей сервера Business следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3a665-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="3a665-177">a)</span><span class="sxs-lookup"><span data-stu-id="3a665-177">a.</span></span> <span data-ttu-id="3a665-178">Если вы выполняете команды на локальном компьютере (например, входите непосредственно на сервер переднего плана): Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с помощью необходимых права пользователя, как описано в **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="3a665-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="3a665-179">б)</span><span class="sxs-lookup"><span data-stu-id="3a665-179">b.</span></span> <span data-ttu-id="3a665-180">Если вы выполняете команды удаленно на другом компьютере (например, входе на свой компьютер и выполняете команды удаленно на сервере переднего плана выпуска Standard): С учетной записью пользователя, назначенной роли CsUserAdministrator или CsAdministrator роль, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="3a665-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3a665-181">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для бизнеса**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="3a665-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3a665-182">Для перемещения отдельных пользователей, используйте командлет Move-CsUser следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3a665-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="3a665-183">Где пользователей для перемещения пользователя Пилар Аккерман и пользователь перемещается из их назначенного в данный момент домашнего пула в пул pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="3a665-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="3a665-184">Для перемещения большого числа пользователей используйте фильтры с помощью командлета **Get-CsUser** и передавайте полученный набор пользователей **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="3a665-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="3a665-185">Совмещение команд **Get-CsUser** и **Move-CsUser** может дать следующий результат:</span><span class="sxs-lookup"><span data-stu-id="3a665-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


