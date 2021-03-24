---
title: 'Управление номерами доступа к телефонным телефонам в Skype для бизнеса Server '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: Сводка. Узнайте, как управлять номерами доступа к телефонным телефонам в Skype для бизнеса Server.
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099155"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="1c0e9-103">Управление номерами доступа к телефонным телефонам в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1c0e9-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="1c0e9-104">**Сводка:** Узнайте, как управлять номерами доступа к телефонным телефонам в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="1c0e9-p101">При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="1c0e9-107">В этом разделе описывается, как просматривать, изменять или удалять существующие номера доступа к телефонным беседам.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="1c0e9-108">Дополнительные сведения о создании начальных номеров доступа к телефонным номерам см. в дополнительных сведениях о настройке телефонных разговоров в [Skype для бизнеса Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="1c0e9-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="1c0e9-109">Просмотр номеров доступа к телефонным телефонам</span><span class="sxs-lookup"><span data-stu-id="1c0e9-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="1c0e9-110">Номера доступа к телефонным телефонам можно просматривать с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1c0e9-111">Просмотр номеров доступа с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="1c0e9-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1c0e9-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1c0e9-113">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1c0e9-114">В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="1c0e9-115">На странице **Номер для телефонного подключения** щелкните номер доступа, который следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="1c0e9-116">В **редактировании** выберите поле **"Сведения** о шоу".</span><span class="sxs-lookup"><span data-stu-id="1c0e9-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1c0e9-117">Просмотр номеров доступа к телефонным номерам с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="1c0e9-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1c0e9-118">Чтобы просмотреть сведения о номерах доступа к телефонным номерам, используйте **кодлет Get-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="1c0e9-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="1c0e9-119">Следующая команда возвращает коллекцию всех номеров доступа к телефонным телефонам, настроенных для использования в организации:</span><span class="sxs-lookup"><span data-stu-id="1c0e9-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="1c0e9-120">Ниже приводится пример типа возвращаемой информации:</span><span class="sxs-lookup"><span data-stu-id="1c0e9-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="1c0e9-121">Дополнительные сведения см. [в рублях Get-CsDialInConferencingAccessNumber.](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1c0e9-121">For more information, see [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="1c0e9-122">Изменение номеров доступа к телефонным конференциам</span><span class="sxs-lookup"><span data-stu-id="1c0e9-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="1c0e9-123">Номера доступа к телефонным номерам можно изменять с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1c0e9-124">Изменение номеров доступа с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="1c0e9-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1c0e9-125">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1c0e9-126">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1c0e9-127">В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="1c0e9-128">На странице **Номер доступа с** телефонным доступом щелкните один из номеров доступа в списке, нажмите кнопку **Изменить** и нажмите кнопку **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c0e9-129">Использование поля поиска для поиска содержимого столбца в списке номеров доступа к диалогу может не дать результатов, которые вы ожидаете.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="1c0e9-130">Вместо этого отсортировать список по интересуемой столбце, чтобы определить номер доступа к диалоговому номеру, который необходимо просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="1c0e9-131">В **отображаемом** номере введите номер телефона, на который звонят пользователи телефонов с общедоступными переключениями телефонных сетей (PSTN), чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="1c0e9-132">Этот номер отображается в приглашениях на собрания и на веб-странице "Параметры параметров телефонной связи".</span><span class="sxs-lookup"><span data-stu-id="1c0e9-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="1c0e9-133">В **имя Display** введите описание номера доступа к диалоговом номеру.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="1c0e9-134">Это имя, связанное с номером доступа к диалогу в результатах поиска Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="1c0e9-135">Это имя отображается в клиенте, когда пользователь вызывает номер доступа.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="1c0e9-136">В **строке URI** введите номер E.164 номера доступа к телефону в формате TEL URI, включая символ + перед номером и за исключением пробелов.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="1c0e9-137">Например, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c0e9-138">Один и тот же URI линии не может быть повторно использовать другой номер доступа к диалоговой связи.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="1c0e9-139">В **SIP URI** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="1c0e9-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="1c0e9-140">В текстовом окне введите уникальный SIP URI для этого номера доступа к диалоговой связи.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="1c0e9-141">Этот SIP URI отображается в различных расположениях, включая сообщения уведомлений об вызовах и предыдущие версии клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c0e9-142">Один и тот же SIP URI не может быть повторно использовать другой номер доступа к диалоговой телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="1c0e9-143">URI SIP не может быть изменен после создания номера доступа.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="1c0e9-144">Единственный способ изменить SIP URI — удалить и воссоздать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="1c0e9-145">В окне выпадающего списка щелкните домен приложения Conferencing Attendant, которое поддерживает этот номер доступа к диалоговому номеру.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="1c0e9-146">В **Пуле** щелкните пул, в который запущен экземпляр помощника по конференциасу, который поддерживает этот номер доступа к диалоговому номеру.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c0e9-147">Если после создания номера доступа необходимо изменить пул, необходимо использовать код **Move-CsApplicationEndpoint** или удалить и воссоздать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="1c0e9-148">На **языке Primary** щелкните язык, на котором будут отыграны подсказки для этого номера доступа к диалоговому номеру.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="1c0e9-149">Основной язык — это язык, который служитель конференциинга использует для ответа на вызов.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="1c0e9-150">Поддерживаемые языки отображаются рядом с каждым номером телефона доступа на веб-странице Параметры телефонных параметров dial-in.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="1c0e9-151">(Необязательный) На дополнительных языках (не более **четырех)** нажмите кнопку **Добавить,** выберите один или несколько дополнительных языков, которые необходимо поддерживать для звонит по этому номеру доступа, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="1c0e9-152">Вы можете выбрать до четырех дополнительных языков для каждого номера доступа к диалоговом номеру.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="1c0e9-153">Пользователи могут выбрать дополнительный язык перед вводом ID конференции при входе на конференцию.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="1c0e9-154">Чтобы добавить область для номера доступа к диалоговой связи, в связанных регионах щелкните **Добавить,** щелкните один или несколько областей, связанных с планами набора для этого номера доступа, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="1c0e9-155">Чтобы удалить область из номера доступа к диалогу, в связанных регионах **щелкните** область, которая необходимо удалить, и нажмите **кнопку Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="1c0e9-156">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1c0e9-157">Изменение номеров доступа к телефонным номерам с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="1c0e9-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1c0e9-158">Чтобы изменить номера доступа к диалогу, используйте **кодлет Set-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="1c0e9-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="1c0e9-159">Следующая команда изменяет свойство DisplayName для номера доступа к диалоговым телефонам с идентификатором sip:RedmondDialIn@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="1c0e9-160">В этом примере отображаемого имени задают номер доступа redmond dial-in:</span><span class="sxs-lookup"><span data-stu-id="1c0e9-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="1c0e9-161">В следующем примере номер доступа к диалоговой связи с идентификатором sip:RedmondDialIn@litwareinc.com, включив в него два региона: Redmond и Seattle.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="1c0e9-162">Для указания городов используется параметр Regions и названия городов (два строковых значения, разделенных запятыми).</span><span class="sxs-lookup"><span data-stu-id="1c0e9-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="1c0e9-163">Обратите внимание, что эта команда завершится с ошибкой, если города Redmond (Редмонд) и Seattle (Сиэтл) не определены в абонентских группах.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="1c0e9-164">Дополнительные сведения см. [в рублях Set-CsDialInConferencingAccessNumber.](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1c0e9-164">For more information, see [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="1c0e9-165">Удаление номера доступа к диалоговой сети</span><span class="sxs-lookup"><span data-stu-id="1c0e9-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="1c0e9-166">Вы можете удалить номер доступа к диалогу с помощью панели управления Skype для бизнес-серверов или с помощью оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1c0e9-167">Удаление номера доступа к диалоговой сети с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="1c0e9-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1c0e9-168">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="1c0e9-169">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1c0e9-170">В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="1c0e9-171">На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="1c0e9-172">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1c0e9-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1c0e9-173">Удаление номера доступа к диалоговой сети с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="1c0e9-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1c0e9-174">Чтобы удалить номер доступа к диалогу, используйте **remove-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="1c0e9-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="1c0e9-175">Следующая команда удаляет номер доступа к диалоговой связи с идентификатором sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="1c0e9-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="1c0e9-176">Следующая команда удаляет все номера доступа к телефонным конференциям, связанные с северо-западным регионом:</span><span class="sxs-lookup"><span data-stu-id="1c0e9-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="1c0e9-177">Следующая команда удаляет все номера доступа к телефонным конференциям, где основным языком является итальянский:</span><span class="sxs-lookup"><span data-stu-id="1c0e9-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="1c0e9-178">Дополнительные сведения см. [в рублях Remove-CsDialInConferencingAccessNumber.](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1c0e9-178">For more information, see [Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
