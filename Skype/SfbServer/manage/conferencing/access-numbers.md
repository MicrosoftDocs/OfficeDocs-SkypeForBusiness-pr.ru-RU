---
title: 'Manage dial-in conferencing access numbers in Skype for Business Server '
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
description: Сводка. Сведения об управлении номерами доступа к телефонной сети в Skype для бизнеса Server.
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806489"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="d1faa-103">Manage dial-in conferencing access numbers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d1faa-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="d1faa-104">**Сводка:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d1faa-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="d1faa-p101">При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="d1faa-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="d1faa-107">В этом разделе описывается, как просматривать, изменять или удалять существующие номера доступа к телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="d1faa-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="d1faa-108">Дополнительные сведения о создании исходных номеров доступа к телефонной сети см. в подстройке "Настройка телефонной сети" в [Skype для бизнеса Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="d1faa-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="d1faa-109">Просмотр номеров доступа кконференции с телефонным присоединением</span><span class="sxs-lookup"><span data-stu-id="d1faa-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="d1faa-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d1faa-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d1faa-111">Просмотр телефонных номеров доступа с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d1faa-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d1faa-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d1faa-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d1faa-113">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d1faa-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d1faa-114">В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.</span><span class="sxs-lookup"><span data-stu-id="d1faa-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="d1faa-115">На странице **Номер для телефонного подключения** щелкните номер доступа, который следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="d1faa-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="d1faa-116">В **окне**"Правка" выберите **"Показать сведения".**</span><span class="sxs-lookup"><span data-stu-id="d1faa-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d1faa-117">Просмотр номеров доступа для телефонного доступа с помощью skype для бизнеса Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d1faa-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d1faa-118">Чтобы просмотреть сведения о номерах доступа для телефонного доступа, используйте **get-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="d1faa-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="d1faa-119">Следующая команда возвращает коллекцию всех номеров доступа к телефонной сети, настроенных для использования в организации:</span><span class="sxs-lookup"><span data-stu-id="d1faa-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="d1faa-120">Ниже приводится пример типа возвращаемой информации:</span><span class="sxs-lookup"><span data-stu-id="d1faa-120">The following is an example of the type of information returned:</span></span>
  
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

<span data-ttu-id="d1faa-121">Дополнительные сведения см. в сведениях [о get-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d1faa-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="d1faa-122">Изменение номеров доступа к телефонной сети</span><span class="sxs-lookup"><span data-stu-id="d1faa-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="d1faa-123">Номера доступа к телефонной сети можно изменять с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d1faa-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d1faa-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="d1faa-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d1faa-125">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d1faa-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d1faa-126">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d1faa-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d1faa-127">В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.</span><span class="sxs-lookup"><span data-stu-id="d1faa-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="d1faa-128">На странице **"Телефонный номер** доступа" выберите один из номеров доступа для телефонного доступа в списке, нажмите кнопку "Изменить" и выберите **"Показать подробности".**</span><span class="sxs-lookup"><span data-stu-id="d1faa-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1faa-129">Использование поля поиска для поиска содержимого столбца в списке номеров доступа с телефонным номером может не дать результатов, которые вы ожидаете.</span><span class="sxs-lookup"><span data-stu-id="d1faa-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="d1faa-130">Вместо этого отсортировать список по интересуемого столбца, чтобы определить номер доступа к телефонной связи, который необходимо просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="d1faa-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="d1faa-131">Введите **в отображаемом** номере номер телефона, который пользователи телефонной сети общего звонков (PSTN) набирают, чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="d1faa-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="d1faa-132">Этот номер отображается в приглашениях на собрания и на веб-странице параметров телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="d1faa-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="d1faa-133">В **отображаемом имени** введите описание номера доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="d1faa-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="d1faa-134">Это имя, связанное с номером доступа для телефонного номера в результатах поиска Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d1faa-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="d1faa-135">Это имя отображается в клиенте, когда пользователь вызывает номер доступа.</span><span class="sxs-lookup"><span data-stu-id="d1faa-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="d1faa-136">В **строке URI** введите номер E.164 номера для телефонного доступа в формате TEL URI, включая символ +перед номером и исключая пробелы.</span><span class="sxs-lookup"><span data-stu-id="d1faa-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="d1faa-137">Например, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="d1faa-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1faa-138">Один и тот же URI линии не может повторно использоваться другим номером доступа к телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="d1faa-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="d1faa-139">В **SIP URI** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="d1faa-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="d1faa-140">В текстовом поле введите уникальный SIP URI для этого номера доступа к телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="d1faa-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="d1faa-141">Этот SIP URI отображается в различных расположениях, включая уведомления о вызовах и предыдущие версии клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="d1faa-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1faa-142">Один и тот же URI SIP не может повторно использоваться другим номером доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="d1faa-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="d1faa-143">URI SIP нельзя изменить после создания номера доступа.</span><span class="sxs-lookup"><span data-stu-id="d1faa-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="d1faa-144">Единственный способ изменить URI SIP — удалить и повторно создать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="d1faa-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="d1faa-145">В поле выпадающего списка щелкните домен приложения помощника по конференцию, которое поддерживает этот номер доступа к телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="d1faa-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="d1faa-146">В **пуле** выберите пул, в который запущен экземпляр помощника по конференцию, который поддерживает этот номер доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="d1faa-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d1faa-147">Если необходимо изменить пул после создания номера доступа, необходимо использовать cmdlet **Move-CsApplicationEndpoint** или удалить и повторно создать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="d1faa-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="d1faa-148">На **основном языке** щелкните язык, на котором будут играть подсказки для этого номера доступа к телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="d1faa-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="d1faa-149">Основной язык — это язык, который помощник по конференцию использует для ответа на вызов.</span><span class="sxs-lookup"><span data-stu-id="d1faa-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="d1faa-150">Поддерживаемые языки отображаются рядом с каждым номером доступа на веб-странице параметров телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="d1faa-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="d1faa-151">(Необязательно) На **дополнительных** языках (не более четырех) нажмите кнопку "Добавить", выберите один или несколько дополнительных языков, которые будут поддерживаться для вызывающих на этот номер доступа по телефонной связи, а затем нажмите кнопку "ОК". </span><span class="sxs-lookup"><span data-stu-id="d1faa-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="d1faa-152">Для каждого номера доступа к телефонной сети можно выбрать до четырех дополнительных языков.</span><span class="sxs-lookup"><span data-stu-id="d1faa-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="d1faa-153">Пользователи могут выбрать дополнительный язык перед вводом ИД конференции при наборе номера для конференции.</span><span class="sxs-lookup"><span data-stu-id="d1faa-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="d1faa-154">Чтобы добавить регион для номера доступа к телефонной связи, в области "Связанные регионы" нажмите кнопку "Добавить", выберите один или несколько регионов, связанных с телефонными планами для этого номера доступа, а затем нажмите кнопку "ОК".  </span><span class="sxs-lookup"><span data-stu-id="d1faa-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="d1faa-155">Чтобы удалить регион из номера доступа по телефонной связи, в области "Связанные регионы" щелкните регион, который нужно удалить, а затем нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="d1faa-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="d1faa-156">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d1faa-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d1faa-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d1faa-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d1faa-158">Чтобы изменить номера доступа к телефонной сети, используйте **cmdlet Set-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="d1faa-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="d1faa-159">Следующая команда изменяет свойство DisplayName для номера доступа к телефонной связи с идентификатором sip:RedmondDialIn@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d1faa-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="d1faa-160">В этом примере для отображаемого имени задается "Redmond Dial-In Access Number":</span><span class="sxs-lookup"><span data-stu-id="d1faa-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="d1faa-161">В следующем примере номер доступа к телефонной связи с идентификатором sip:RedmondDialIn@litwareinc.com включает два региона: Редмонд и Сиэтл.</span><span class="sxs-lookup"><span data-stu-id="d1faa-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="d1faa-162">Для указания городов используется параметр Regions и названия городов (два строковых значения, разделенных запятыми).</span><span class="sxs-lookup"><span data-stu-id="d1faa-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="d1faa-163">Обратите внимание, что эта команда завершится с ошибкой, если города Redmond (Редмонд) и Seattle (Сиэтл) не определены в абонентских группах.</span><span class="sxs-lookup"><span data-stu-id="d1faa-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="d1faa-164">Дополнительные сведения см. в [подстроке Set-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d1faa-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="d1faa-165">Удаление номера доступа к присоединению к телефонной сети</span><span class="sxs-lookup"><span data-stu-id="d1faa-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="d1faa-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d1faa-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d1faa-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="d1faa-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d1faa-168">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d1faa-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="d1faa-169">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d1faa-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d1faa-170">В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.</span><span class="sxs-lookup"><span data-stu-id="d1faa-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="d1faa-171">На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d1faa-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="d1faa-172">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d1faa-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d1faa-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d1faa-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d1faa-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="d1faa-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="d1faa-175">Следующая команда удаляет номер доступа к телефонной связи с удостоверением sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="d1faa-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="d1faa-176">Следующая команда удаляет все номера доступа к телефонной связи, связанные с регионом "Северо-Запад":</span><span class="sxs-lookup"><span data-stu-id="d1faa-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="d1faa-177">Следующая команда удаляет все номера доступа к телефонной сети, где основным языком является итальянский:</span><span class="sxs-lookup"><span data-stu-id="d1faa-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="d1faa-178">Дополнительные сведения см. в [remove-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d1faa-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

