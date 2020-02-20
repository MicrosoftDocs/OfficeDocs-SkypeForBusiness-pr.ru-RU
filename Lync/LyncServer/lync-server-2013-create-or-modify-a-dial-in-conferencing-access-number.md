---
title: 'Lync Server 2013: создание или изменение номера доступа к конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2793a37fcac58afdf3e996094bcb8d2ff8f5a2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="e9d44-102">Создание или изменение номера доступа к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9d44-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9d44-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e9d44-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e9d44-104">Чтобы создать или изменить номер доступа к конференц-связи с телефонным подключением, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e9d44-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9d44-105">Перед созданием нового номера доступа для телефонного подключения необходимо установить в абонентской плане регион конференц-связи с телефонным подключением, связанный с новым номером доступа для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="e9d44-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="e9d44-106">Несколько абонентских группы могут использовать один и тот же регион.</span><span class="sxs-lookup"><span data-stu-id="e9d44-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="e9d44-107">Создание или изменение номера доступа с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="e9d44-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="e9d44-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e9d44-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e9d44-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9d44-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e9d44-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e9d44-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e9d44-111">В левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="e9d44-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="e9d44-112">На странице **номер доступа для телефонного подключения** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="e9d44-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e9d44-113">Нажмите кнопку **создать** , чтобы открыть **новый номер доступа для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="e9d44-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="e9d44-114">Выберите в списке один из номеров для телефонного подключения, нажмите кнопку **изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="e9d44-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9d44-115">Использование поля поиска для поиска контента столбца в списке номеров доступа с телефонным подключением может не дать ожидаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="e9d44-115">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="e9d44-116">Вместо этого отсортируйте список по интересующему столбцу, чтобы определить номер доступа для телефонного подключения, который вы хотите просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="e9d44-116">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="e9d44-117">В поле **отображаемый номер**введите телефонный номер, который абоненты телефонной сети общего пользования (PSTN) набирается для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="e9d44-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9d44-118">Этот номер отображается в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e9d44-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="e9d44-119">В поле **Отображаемое имя**введите описание номера доступа для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="e9d44-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="e9d44-120">Это имя, связанное с номером доступа для телефонного подключения в результатах поиска Lync.</span><span class="sxs-lookup"><span data-stu-id="e9d44-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9d44-121">Это имя отображается в клиенте, когда пользователь вызывает номер доступа.</span><span class="sxs-lookup"><span data-stu-id="e9d44-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="e9d44-122">В поле **URI линии**введите номер E. 164 номера доступа для телефонного подключения в формате URI TEL, включая символ + перед номером и без пробелов.</span><span class="sxs-lookup"><span data-stu-id="e9d44-122">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="e9d44-123">Например, Tel: + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="e9d44-123">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9d44-124">Один и тот же URI линии не может повторно использоваться другим номером доступа к Конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e9d44-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="e9d44-125">В **URI SIP**выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e9d44-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="e9d44-126">В текстовом поле введите уникальный URI SIP для номера доступа к конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e9d44-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="e9d44-127">Этот URI SIP отображается в различных местах, в том числе в сообщениях уведомлений о вызовах и предыдущих версиях клиентов Communicator.</span><span class="sxs-lookup"><span data-stu-id="e9d44-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e9d44-128">Один и тот же URI SIP не может повторно использоваться другим номером доступа к Конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e9d44-128">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="e9d44-129">После создания номера доступа невозможно изменить URI SIP.</span><span class="sxs-lookup"><span data-stu-id="e9d44-129">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="e9d44-130">Единственный способ изменить URI SIP состоит в удалении и повторном создании номера доступа.</span><span class="sxs-lookup"><span data-stu-id="e9d44-130">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="e9d44-131">В раскрывающемся списке выберите домен приложения-помощника по конференц-связи, который поддерживает этот номер доступа.</span><span class="sxs-lookup"><span data-stu-id="e9d44-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="e9d44-132">В разделе **пул**выберите пул, на котором запущен экземпляр помощника по конференц-связи, поддерживающий этот номер доступа.</span><span class="sxs-lookup"><span data-stu-id="e9d44-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9d44-133">Если необходимо изменить пул после создания номера доступа, необходимо использовать командлет <STRONG>Move – CsApplicationEndpoint</STRONG> или удалить и повторно создать номер доступа.</span><span class="sxs-lookup"><span data-stu-id="e9d44-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="e9d44-134">В разделе **основной язык**выберите язык, на котором воспроизводится приглашение для этого номера доступа с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e9d44-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9d44-135">Основной язык — это язык, который помощник по конференциям использует для ответа на звонок.</span><span class="sxs-lookup"><span data-stu-id="e9d44-135">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="e9d44-136">Поддерживаемые языки отображаются вместе с каждым номером доступа на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="e9d44-136">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="e9d44-137">Необязательно На **дополнительных языках (не более четырех)** нажмите кнопку **Добавить**, выберите один или несколько дополнительных языков, которые требуется поддерживать для абонентов для этого номера доступа с телефонным подключением, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9d44-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9d44-138">Для каждого номера доступа по телефонной линии можно выбрать до четырех дополнительных языков.</span><span class="sxs-lookup"><span data-stu-id="e9d44-138">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="e9d44-139">Пользователи могут выбрать дополнительный язык, прежде чем вводить идентификатор конференции при подключении к Конференции.</span><span class="sxs-lookup"><span data-stu-id="e9d44-139">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="e9d44-140">Чтобы добавить регион для номера доступа с телефонным подключением, в разделе **связанные регионы**нажмите кнопку **Добавить**, выберите одну или несколько регионов, связанных с абонентской абонентской абонентской абонентской учетной записью, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9d44-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="e9d44-141">Чтобы удалить регион из номера доступа с телефонным подключением, в разделе **связанные регионы**выберите регион, который необходимо удалить, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e9d44-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="e9d44-142">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="e9d44-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

