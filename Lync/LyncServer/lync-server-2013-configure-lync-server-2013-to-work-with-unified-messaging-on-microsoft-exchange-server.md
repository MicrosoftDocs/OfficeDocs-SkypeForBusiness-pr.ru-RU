---
title: 'Lync Server 2013: настройка Lync Server 2013 для работы с единой системой обмена сообщениями на Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="ccba6-102">Настройка Lync Server 2013 для работы с единой системой обмена сообщениями на Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ccba6-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="ccba6-103">_**Тема последнего изменения:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="ccba6-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="ccba6-104">Для этого шага требуется служебная программа интеграции единой системы обмена сообщениями (Оксумутил. exe).</span><span class="sxs-lookup"><span data-stu-id="ccba6-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="ccba6-105">Это средство находится на сервере Lync Server 2013 в разделе.. \\Программные\\файлы:\\общие файлы. папка\\поддержки Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ccba6-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="ccba6-106">Запуск служебной программы интеграции единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="ccba6-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="ccba6-107">Служебную программу интеграции UM необходимо запускать из учетной записи пользователя со следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="ccba6-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="ccba6-108">Членство в группах Рткуниверсалсерверадминс и Рткуниверсалусерадминс (которая включает разрешение на чтение параметров единой системы обмена сообщениями Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="ccba6-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="ccba6-109">Права пользователей в домене для создания объектов контакта в указанном контейнере подразделения.</span><span class="sxs-lookup"><span data-stu-id="ccba6-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="ccba6-110">При запуске утилиты интеграции Exchange UM выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="ccba6-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="ccba6-111">Создание объектов контактов для каждого автосекретаря и номера абонентского доступа, которые будут использоваться пользователями корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ccba6-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="ccba6-112">Проверка того, что имя каждой из корпоративных абонентских групп совпадает с соответствующим контекстом телефонной группы единой системы обмена сообщениями (UM) для абонентского плана.</span><span class="sxs-lookup"><span data-stu-id="ccba6-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="ccba6-113">Это соответствие необходимо только в том случае, если абонентская группа UM работает в *более ранней* версии Exchange, чем Exchange 2010 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="ccba6-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccba6-114">Перед запуском служебной программы интеграции UM убедитесь в том, что вы выполнили описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ccba6-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="ccba6-115">Создание одной или нескольких абонентских групп UM, описанных в документации по Exchange.</span><span class="sxs-lookup"><span data-stu-id="ccba6-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="ccba6-116">Для сервера Microsoft Exchange Server 2010 &quot;&quot; в <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>разделе Создание абонентской группы единой системы обмена сообщениями:</span><span class="sxs-lookup"><span data-stu-id="ccba6-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="ccba6-117">Для Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) &quot;Узнайте, как создать телефонную группу для единого обмена&quot; сообщениями с помощью URI по адресу <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span><span class="sxs-lookup"><span data-stu-id="ccba6-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="ccba6-118">Создайте одну или несколько соответствующих абонентских планов Lync Server, как описано в разделе <a href="lync-server-2013-create-a-dial-plan.md">Создание абонентской группы в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ccba6-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="ccba6-119">При использовании более ранней версии Exchange, чем Microsoft Exchange Server 2010 с пакетом обновления 1 (SP1), необходимо ввести полное доменное имя (FQDN) соответствующей абонентской группы для единой системы обмена сообщениями Exchange (UM) в Lync Server 2013 Dialing Plan (одноименная телефонная группа) <STRONG> </STRONG>поле.</span><span class="sxs-lookup"><span data-stu-id="ccba6-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="ccba6-120">Если вы используете Microsoft Exchange Server 2010 или новейшую версию пакета обновления, это не требуется для сопоставления имен абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="ccba6-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="ccba6-121">Создайте автосекретарь и убедитесь, что оба номера для абонента и номера автосекретаря находятся в формате E. 164.</span><span class="sxs-lookup"><span data-stu-id="ccba6-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="ccba6-122">Запуск служебной программы интеграции единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="ccba6-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="ccba6-123">На сервере переднего плана откройте командную строке и введите **CD% COMMONPROGRAMFILES%\\Microsoft Lync Server 2013\\**, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ccba6-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="ccba6-124">Введите **оксумутил. exe**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ccba6-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="ccba6-125">Нажмите кнопку **загрузить данные** , чтобы найти всех доверенных лесов Exchange.</span><span class="sxs-lookup"><span data-stu-id="ccba6-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="ccba6-126">В списке **абонентские группы SIP** выберите абонентскую группу UM, для которой вы хотите создать объекты контактов, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ccba6-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="ccba6-127">В поле **контакт** выберите подразделение по умолчанию или нажмите кнопку **Обзор** , чтобы запустить **средство выбора**подразделений.</span><span class="sxs-lookup"><span data-stu-id="ccba6-127">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**.</span></span> <span data-ttu-id="ccba6-128">В диалоговом окне **Выбор** подразделений выберите подразделение и нажмите кнопку **ОК**или щелкните создать подразделение, чтобы создать новое подразделение в корневом или другом подразделении домена (например, "OU = Special Accounts, DC = FourthCoffee, DC = com"). \*\*\*\* , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccba6-128">In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccba6-129">Различающееся имя (DN), которое вы выбрали или создали, будет отображаться в поле " <STRONG>подразделение</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="ccba6-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="ccba6-130">В поле **имя** либо подтвердите имя абонентской группы по умолчанию, либо введите новое отображаемое имя для создаваемого объекта контакта.</span><span class="sxs-lookup"><span data-stu-id="ccba6-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccba6-131">Например, если вы создаете объект контакта доступа для абонента, вы можете просто присвоить ему имя абоненту Access.</span><span class="sxs-lookup"><span data-stu-id="ccba6-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="ccba6-132">В поле **адрес SIP** введите адрес SIP по умолчанию или новый адрес SIP.</span><span class="sxs-lookup"><span data-stu-id="ccba6-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccba6-133">Если вы вводите новый SIP-адрес, он должен начинаться с <STRONG>SIP:</STRONG> (то есть "SIP:", включая двоеточие).</span><span class="sxs-lookup"><span data-stu-id="ccba6-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="ccba6-134">В списке **сервер или пул** выберите сервер стандартного выпуска Standard или пул переднего плана, в котором нужно включить объект контакта.</span><span class="sxs-lookup"><span data-stu-id="ccba6-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccba6-135">Предпочтительнее, что выбранный пул используется в том же пуле, где развернуты пользователи, поддерживающие корпоративную голосовую почту и Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="ccba6-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="ccba6-136">В списке **номер телефона** выберите либо **Введите номер телефона** , либо **Используйте этот телефонный номер из UM Exchange** и введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="ccba6-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="ccba6-137">В списке **Тип контакта** выберите тип контакта, который вы хотите создать, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccba6-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="ccba6-138">Повторите действия 1 – 10 для дополнительных объектов контакта, которые вы хотите создать.</span><span class="sxs-lookup"><span data-stu-id="ccba6-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccba6-139">Для каждого автосекретаря нужно создать хотя бы один контакт.</span><span class="sxs-lookup"><span data-stu-id="ccba6-139">You should create at least one contact for each auto attendant.</span></span> <span data-ttu-id="ccba6-140">Если вам нужен внешний доступ, вам также нужен контакт Access и задать прямые номера набора номера.</span><span class="sxs-lookup"><span data-stu-id="ccba6-140">If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="ccba6-141">Чтобы убедиться в том, что объекты контакта созданы, откройте оснастку "пользователи и компьютеры Active Directory" и выберите подразделение, в котором были созданы объекты.</span><span class="sxs-lookup"><span data-stu-id="ccba6-141">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created.</span></span> <span data-ttu-id="ccba6-142">Объекты контакта должны отображаться в области сведений.</span><span class="sxs-lookup"><span data-stu-id="ccba6-142">The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="ccba6-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="ccba6-143"></span></span></div>

