---
title: 'Lync Server 2013: создание или изменение номера доступа к конференции с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="3e75e-102">Создание или изменение номера доступа к конференции с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e75e-102">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e75e-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="3e75e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="3e75e-104">Если вы хотите создать или изменить номер доступа к конференц-связи с телефонным подключением, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3e75e-104">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e75e-105">Прежде чем создавать новый номер доступа для телефонного подключения, необходимо задать в абонентской группе регион конференц-связи с телефонным подключением, который связан с новым номером доступа для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="3e75e-105">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="3e75e-106">Несколько абонентских группы могут использовать один и тот же регион.</span><span class="sxs-lookup"><span data-stu-id="3e75e-106">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="3e75e-107">Чтобы создать или изменить номер доступа для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="3e75e-107">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="3e75e-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3e75e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e75e-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e75e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e75e-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e75e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e75e-111">На левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="3e75e-111">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="3e75e-112">На странице **Номер для телефонного подключения** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="3e75e-112">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3e75e-113">Нажмите **Создать**, чтобы открыть диалоговое окно **Создание номера для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="3e75e-113">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="3e75e-114">Выберите один из номеров для телефонного подключения, щелкните элемент **Правка**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="3e75e-114">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3e75e-p103">Использование поля поиска для поиска содержимого столбца в списке номеров доступа по телефонной линии может не дать желаемый результат. Вместо этого рекомендуется упорядочить список по интересующему столбцу, чтобы найти номер доступа по телефонной линии, который требуется просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="3e75e-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="3e75e-117">В поле **Отображаемый номер** введите телефонный номер, который набирают пользователи телефонной сети общего пользования (ТСОП), чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="3e75e-117">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e75e-118">Этот номер отображается в приглашениях на собрание и на веб-странице параметров конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="3e75e-118">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="3e75e-119">В поле **Отображаемое имя** введите описание для этого номера для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="3e75e-119">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="3e75e-120">Это имя, связанное с номером доступа для телефонного подключения в результатах поиска Lync.</span><span class="sxs-lookup"><span data-stu-id="3e75e-120">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e75e-121">Это имя отображается в клиенте, когда пользователь набирает этот номер доступа.</span><span class="sxs-lookup"><span data-stu-id="3e75e-121">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="3e75e-p105">В поле **URI линии** введите номер E.164 для номера для телефонного подключения в формате TEL URI, включая символ + (плюс) перед номером и исключая пробелы. Например, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="3e75e-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e75e-124">Этот же самый URI линии не может использоваться другим номером доступа к конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="3e75e-124">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="3e75e-125">В разделе **SIP URI** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3e75e-125">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="3e75e-126">В текстовом поле введите уникальный SIP URI для этого номера доступа к конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="3e75e-126">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="3e75e-127">Этот универсальный код ресурса (URI) SIP отображается в различных расположениях, в том числе в сообщениях уведомлений о вызовах и предыдущих версиях клиентов Communicator.</span><span class="sxs-lookup"><span data-stu-id="3e75e-127">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3e75e-p107">Этот же самый SIP URI не может использоваться другим номером доступа к конференции с телефонным подключением. Этот SIP URI нельзя изменить после создания номера доступа. Единственный способ изменить SIP URI для номера доступа заключается в в удалении и повторном создании этого номера доступа.</span><span class="sxs-lookup"><span data-stu-id="3e75e-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="3e75e-131">В раскрывающемся списке выберите домен приложения, которое поддерживает этот номер доступа для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="3e75e-131">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="3e75e-132">В области **Пул** выберите пул, в котором работает экземпляр помощника по конференц-связи, поддерживающий этот номер для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="3e75e-132">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e75e-133">Если требуется изменить пул после создания номера доступа, то необходимо использовать командлет <STRONG>Move-CsApplicationEndpoint</STRONG> или удалить этот номер доступа и создать его заново.</span><span class="sxs-lookup"><span data-stu-id="3e75e-133">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="3e75e-134">В области **Основной язык** выберите язык, на котором будут воспроизводиться приглашения для этого номера для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="3e75e-134">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e75e-p108">Основной язык – это язык, который помощник по конференц-связи использует для ответа на вызов. Поддерживаемые языки отображаются на веб-странице параметров конференц-связи с телефонным подключением рядом с каждым номером доступа.</span><span class="sxs-lookup"><span data-stu-id="3e75e-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="3e75e-137">В области **Дополнительные языки (не более четырех)** нажмите **Добавить**, выберите дополнительные языки, которые требуется поддерживать для абонентов, набирающих этот номер для телефонного подключения, и нажмите кнопку **ОК** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="3e75e-137">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e75e-p109">Для каждого номера доступа по телефонной линии можно выбрать вплоть до четырех дополнительных языков. Пользователи могут выбирать дополнительный язык до ввода идентификатора конференции, когда они набирают номер доступа к конференции.</span><span class="sxs-lookup"><span data-stu-id="3e75e-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="3e75e-140">Чтобы добавить регион для номера доступа для телефонного подключения, в разделе **связанные регионы**нажмите кнопку **Добавить**, выберите одну или несколько регионов, связанных с абонентской панелью для этого номера доступа, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3e75e-140">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="3e75e-141">Чтобы удалить регион из номера для телефонного подключения, в разделе **Связанные регионы** выберите регион, который требуется удалить, и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3e75e-141">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="3e75e-142">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="3e75e-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

