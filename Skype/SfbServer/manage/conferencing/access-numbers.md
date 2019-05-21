---
title: 'Управление номерами доступа для конференц-связи с телефонным подключением в Skype для бизнеса Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: Сводка. сведения о том, как управлять номерами доступа для конференц-связи с телефонным подключением в Skype для бизнеса Server.
ms.openlocfilehash: e41011c4ba06da7f05d8cb1a52717e707cd2f8bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289036"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="41c47-103">Управление номерами доступа для конференц-связи с телефонным подключением в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41c47-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="41c47-104">**Сводка:** Сведения о том, как управлять номерами доступа для конференц-связи с телефонным подключением в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41c47-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="41c47-105">При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции.</span><span class="sxs-lookup"><span data-stu-id="41c47-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="41c47-106">Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="41c47-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="41c47-107">В этом разделе описывается, как просматривать, изменять или удалять существующие номера доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="41c47-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="41c47-108">Дополнительные сведения о создании начальных номеров доступа для телефонного подключения можно найти [в разделе Настройка конференц-связи с телефонным подключением в Skype для бизнеса Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="41c47-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="41c47-109">Просмотр номеров доступа для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="41c47-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="41c47-110">Номера доступа для конференц-связи с телефонным подключением можно просматривать с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41c47-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="41c47-111">Просмотр номеров доступа для телефонного подключения с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41c47-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="41c47-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="41c47-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="41c47-113">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41c47-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="41c47-114">В левой панели навигации выберите **Конференция**, а затем щелкните **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="41c47-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="41c47-115">На странице **Номер для телефонного подключения** щелкните номер доступа, который следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="41c47-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="41c47-116">В разделе **Изменить** установите флажок **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="41c47-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="41c47-117">Просмотр номеров доступа для телефонного подключения с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41c47-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="41c47-118">Для просмотра информации о номерах для телефонного подключения используется командлет **Get-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="41c47-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="41c47-119">Следующая команда возвращает коллекцию всех номеров доступа конференц-связи с телефонным подключением, настроенных для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="41c47-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="41c47-120">Ниже приведен пример типа возвращаемой информации.</span><span class="sxs-lookup"><span data-stu-id="41c47-120">The following is an example of the type of information returned:</span></span>
  
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

<span data-ttu-id="41c47-121">Дополнительные сведения можно найти в [статьях Get-ксдиалинконференЦингакцесснумбер](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="41c47-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="41c47-122">Изменение номеров доступа для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="41c47-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="41c47-123">Вы можете изменить номера доступа для телефонного подключения с помощью панели управления Skype для бизнеса Server или консоли управления в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41c47-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="41c47-124">Изменение номеров доступа для телефонного подключения с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41c47-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="41c47-125">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="41c47-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="41c47-126">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41c47-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="41c47-127">В левой панели навигации выберите **Конференция**, а затем щелкните **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="41c47-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="41c47-128">На странице **Номер для телефонного подключения** выберите один из номеров для телефонного подключения, щелкните **Изменить**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="41c47-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41c47-p103">Использование поля поиска для поиска содержимого столбца в списке номеров доступа по телефонной линии может не дать желаемый результат. Вместо этого рекомендуется упорядочить список по интересующему столбцу, чтобы найти номер доступа по телефонной линии, который требуется просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="41c47-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="41c47-131">В поле **Отображаемый номер** введите телефонный номер, который набирают пользователи телефонной сети общего пользования (ТСОП), чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="41c47-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="41c47-132">Этот номер отображается в приглашениях на собрание и на веб-странице параметров конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="41c47-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="41c47-133">В поле **Отображаемое имя** введите описание для этого номера для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="41c47-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="41c47-134">Это имя, связанное с номером доступа для телефонного подключения в результатах поиска в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="41c47-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="41c47-135">Это имя отображается в клиенте, когда пользователь набирает этот номер доступа.</span><span class="sxs-lookup"><span data-stu-id="41c47-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="41c47-p105">В поле **URI линии** введите номер E.164 для номера для телефонного подключения в формате TEL URI, включая символ + (плюс) перед номером и исключая пробелы. Например, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="41c47-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41c47-138">Этот же самый URI линии не может использоваться другим номером доступа к конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="41c47-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="41c47-139">В разделе **SIP URI** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="41c47-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="41c47-140">В текстовом поле введите уникальный SIP URI для этого номера доступа к конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="41c47-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="41c47-141">Этот универсальный код ресурса (URI) SIP отображается в различных расположениях, включая и не ограничиваются сообщениями уведомления о звонках и предыдущими версиями клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="41c47-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41c47-p107">Этот же самый SIP URI не может использоваться другим номером доступа к конференции с телефонным подключением. Этот SIP URI нельзя изменить после создания номера доступа. Единственный способ изменить SIP URI для номера доступа заключается в в удалении и повторном создании этого номера доступа.</span><span class="sxs-lookup"><span data-stu-id="41c47-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="41c47-145">В раскрывающемся списке выберите домен приложения, которое поддерживает этот номер доступа для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="41c47-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="41c47-146">В области **Пул** выберите пул, в котором работает экземпляр помощника по конференц-связи, поддерживающий этот номер для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="41c47-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41c47-147">Если требуется изменить пул после создания номера доступа, то необходимо использовать командлет **Move-CsApplicationEndpoint** или удалить этот номер доступа и создать его заново.</span><span class="sxs-lookup"><span data-stu-id="41c47-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="41c47-148">В области **Основной язык** выберите язык, на котором будут воспроизводиться приглашения для этого номера для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="41c47-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="41c47-p108">Основной язык – это язык, который помощник по конференц-связи использует для ответа на вызов. Поддерживаемые языки отображаются на веб-странице параметров конференц-связи с телефонным подключением рядом с каждым номером доступа.</span><span class="sxs-lookup"><span data-stu-id="41c47-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="41c47-151">В области **Дополнительные языки (не более четырех)** нажмите **Добавить**, выберите дополнительные языки, которые требуется поддерживать для абонентов, набирающих этот номер для телефонного подключения, и нажмите кнопку **ОК** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="41c47-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="41c47-p109">Для каждого номера доступа по телефонной линии можно выбрать вплоть до четырех дополнительных языков. Пользователи могут выбирать дополнительный язык до ввода идентификатора конференции, когда они набирают номер доступа к конференции.</span><span class="sxs-lookup"><span data-stu-id="41c47-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="41c47-154">Чтобы добавить регион для номера доступа для телефонного подключения, в разделе **связанные регионы**нажмите кнопку **Добавить**, выберите одну или несколько регионов, связанных с абонентской панелью для этого номера доступа, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="41c47-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="41c47-155">Чтобы удалить регион из номера для телефонного подключения, в разделе **Связанные регионы** выберите регион, который требуется удалить, и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="41c47-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="41c47-156">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="41c47-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="41c47-157">Изменение номеров доступа для телефонного подключения с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41c47-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="41c47-158">Для изменения номеров для телефонного подключения используется командлет **Set-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="41c47-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="41c47-p110">Приведенная ниже команда изменяет значение свойства DisplayName для номера доступа к конференц-связи с телефонным подключением с идентификатором sip:RedmondDialIn@litwareinc.com. В этом примере в качестве отображаемого имени задается "Redmond Dial-In Access Number" (Номер для телефонного подключения в г. Редмонд).</span><span class="sxs-lookup"><span data-stu-id="41c47-p110">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com. In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="41c47-p111">Команда, показанная в следующем примере, изменяет номер доступа к конференц-связи с телефонным подключением с идентификатором sip:RedmondDialIn@litwareinc.com, добавляя города Redmond (Редмонд) и Seattle (Сиэтл). Для указания городов используется параметр Regions и названия городов (два строковых значения, разделенных запятыми). Обратите внимание, что эта команда завершится с ошибкой, если города Redmond (Редмонд) и Seattle (Сиэтл) не определены в абонентских группах.</span><span class="sxs-lookup"><span data-stu-id="41c47-p111">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle. To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas). Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="41c47-164">Дополнительные сведения можно найти в разделе [Set-ксдиалинконференЦингакцесснумбер](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="41c47-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="41c47-165">Удаление номера доступа к конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="41c47-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="41c47-166">Номер доступа к конференц-связи с телефонным подключением можно удалить с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41c47-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="41c47-167">Удаление номера доступа к конференц-связи с телефонным подключением с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41c47-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="41c47-168">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="41c47-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="41c47-169">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="41c47-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="41c47-170">В левой панели навигации выберите **Конференция**, а затем щелкните **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="41c47-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="41c47-171">На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="41c47-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="41c47-172">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="41c47-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="41c47-173">Удаление номера доступа для конференц-связи с телефонным подключением с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="41c47-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="41c47-174">Для удаления номера доступа к конференции с телефонным подключением используется командлет **Remove-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="41c47-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="41c47-175">Приведенная ниже команда служит для удаления номера доступа к конференц-связи с телефонным подключением с идентификатором sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="41c47-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="41c47-176">Следующая команда служит для удаления всех номеров доступа к конференц-связи с телефонным подключением, связанных с регионом "Северо-запад":</span><span class="sxs-lookup"><span data-stu-id="41c47-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="41c47-177">Следующая команда служит для удаления всех номеров доступа к конференц-связи с телефонным подключением, для которых итальянский — основной язык:</span><span class="sxs-lookup"><span data-stu-id="41c47-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="41c47-178">Дополнительные сведения можно найти в разделе [Remove-ксдиалинконференЦингакцесснумбер](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="41c47-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

