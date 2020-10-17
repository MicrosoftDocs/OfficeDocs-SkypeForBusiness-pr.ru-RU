---
title: 'Lync Server 2013: Настройка Lync Server 2013 для работы с единой системой обмена сообщениями в Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b297a505b1a12335e545895e0203ffc0e29c7354
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507636"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="de5b0-102">Настройка Lync Server 2013 для работы с единой системой обмена сообщениями на сервере Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="de5b0-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="de5b0-103">_**Последнее изменение темы:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="de5b0-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="de5b0-104">Для этого шага требуется средство интеграции Exchange UM (OcsUmUtil.exe).</span><span class="sxs-lookup"><span data-stu-id="de5b0-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="de5b0-105">Это средство находится на сервере Lync Server 2013 в... \\ Program Files \\ Common Files — \\ Папка поддержки Microsoft Lync Server 2013 \\ .</span><span class="sxs-lookup"><span data-stu-id="de5b0-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="de5b0-106">Запуск средства интеграции Exchange UM</span><span class="sxs-lookup"><span data-stu-id="de5b0-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="de5b0-107">Средство интеграции Exchange UM необходимо запустить под учетной записью пользователя со следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="de5b0-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="de5b0-108">членство в группах RtcUniversalUserAdmins и RTCUniversalServerAdmins (с разрешениями на чтение параметров единой системы обмена сообщениями Exchange Server);</span><span class="sxs-lookup"><span data-stu-id="de5b0-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="de5b0-109">права пользователя в домене, чтобы создавать объекты контактов в указанном контейнере подразделения.</span><span class="sxs-lookup"><span data-stu-id="de5b0-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="de5b0-110">При запуске средства интеграции Exchange UM оно выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="de5b0-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="de5b0-111">Создает объекты контактов для каждого автосекретаря и номер абонентского доступа, который будет использоваться пользователями корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="de5b0-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="de5b0-112">Проверяет, соответствует ли имя каждой корпоративной абонентской группы, соответствующему контексту телефонной группы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="de5b0-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="de5b0-113">Это совпадение необходимо только в том случае, если абонентская группа единой системы обмена сообщениями работает в *более ранней* версии Exchange, чем Exchange 2010 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="de5b0-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de5b0-114">Перед запуском средства интеграции Exchange UM убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="de5b0-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="de5b0-115">Создайте одну или несколько абонентских групп единой системы обмена сообщениями Exchange, как описано в документации по продукту Exchange.</span><span class="sxs-lookup"><span data-stu-id="de5b0-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="de5b0-116">&quot;В разделе Создание абонентской группы единой системы обмена сообщениями для Microsoft Exchange Server 2010 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> .</span><span class="sxs-lookup"><span data-stu-id="de5b0-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="de5b0-117">Для Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) вы можете ознакомиться со статьей &quot; Создание абонентской группы URI SIP единой системы обмена сообщениями &quot; по адресу <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> .</span><span class="sxs-lookup"><span data-stu-id="de5b0-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="de5b0-118">Создайте одну или несколько соответствующих абонентских группы Lync Server, как описано в разделе <a href="lync-server-2013-create-a-dial-plan.md">Create a Dialing Plan in Lync server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="de5b0-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="de5b0-119">Если вы используете более раннюю версию Exchange, чем Microsoft Exchange Server 2010 с пакетом обновления 1 (SP1), необходимо ввести полное доменное имя соответствующей абонентской группы SIP единой системы обмена сообщениями Exchange в поле <STRONG>простого имени</STRONG> абонентской группы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de5b0-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="de5b0-120">Если вы используете Microsoft Exchange Server 2010 с пакетом обновления 1 (SP1) или более поздней версии, это имя не требуется.</span><span class="sxs-lookup"><span data-stu-id="de5b0-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="de5b0-121">Создайте автосекретаря и убедитесь, что номер абонентского доступа и номера автосекретаря указаны в формате E.164.</span><span class="sxs-lookup"><span data-stu-id="de5b0-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="de5b0-122">Запуск средства интеграции Exchange UM</span><span class="sxs-lookup"><span data-stu-id="de5b0-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="de5b0-123">На сервере переднего плана откройте командную строку и введите **CD% COMMONPROGRAMFILES%% \\ \\ поддержки Microsoft Lync Server 2013**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="de5b0-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="de5b0-124">Введите **OcsUmUtil.exe**, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="de5b0-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="de5b0-125">Нажмите кнопку **Загрузить данные**, чтобы найти все доверенные леса Exchange.</span><span class="sxs-lookup"><span data-stu-id="de5b0-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="de5b0-126">В списке \*\*Абонентские группы SIP \*\* выберите абонентскую группу SIP единой системы обмена сообщениями, для которой требуется создать объекты контактов, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="de5b0-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="de5b0-p104">В поле **Контакт** примите подразделение по умолчанию или нажмите кнопку **Обзор** для запуска **средства выбора подразделения**. В поле **Средство выбора подразделения** можно выбрать подразделение и нажать кнопку **ОК** или можно нажать кнопку **Создать подразделение**, чтобы создать подразделение в корне или или любом другом подразделении в домене (например, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), а затем нажать кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de5b0-p104">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**. In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de5b0-129">Различающееся имя (DN) выбранного или созданного подразделения теперь отображается в поле <STRONG>Подразделение</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="de5b0-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="de5b0-130">В поле **Имя** примите выбранное по умолчанию имя абонентской группы или введите новое отображаемое имя для создаваемого объекта контактов.</span><span class="sxs-lookup"><span data-stu-id="de5b0-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de5b0-131">Например, при создании объекта контакта абонентского доступа вы можете просто указать имя "Абонентский доступ".</span><span class="sxs-lookup"><span data-stu-id="de5b0-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="de5b0-132">В поле **SIP- адрес** примите выбранный по умолчанию SIP-адрес или введите новый SIP-адрес.</span><span class="sxs-lookup"><span data-stu-id="de5b0-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de5b0-133">Если ввести новый SIP-адрес, он должен начинаться с <STRONG>SIP:</STRONG> (то есть, "SIP:" с двоеточием).</span><span class="sxs-lookup"><span data-stu-id="de5b0-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="de5b0-134">В списке **сервер или пул** выберите сервер Standard Edition или пул переднего плана, в котором должен быть включен объект Contact.</span><span class="sxs-lookup"><span data-stu-id="de5b0-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de5b0-135">Предпочтительным выбранным пулом является тот же пул, где разворачиваются пользователи, для которых включена поддержка корпоративной голосовой связи и единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="de5b0-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="de5b0-136">В списке **Номер телефона** выберите **Ввести номер телефона** или **Использовать этот пилотный номер из единой системы обмена сообщениями Exchange**, а затем введите номер телефона.</span><span class="sxs-lookup"><span data-stu-id="de5b0-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="de5b0-137">В списке **Тип контакта** выберите тип контакт, который требуется создать, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="de5b0-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="de5b0-138">Повторите шаги 1-10 для дополнительных объектов контактов, которые нужно создать.</span><span class="sxs-lookup"><span data-stu-id="de5b0-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de5b0-p105">Необходимо создать по крайней мере один контакт для каждого автосекретаря. Если вам требуется внешний доступ, также нужен контакт абонентского доступа и номера DID.</span><span class="sxs-lookup"><span data-stu-id="de5b0-p105">You should create at least one contact for each auto attendant. If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="de5b0-p106">Чтобы убедиться, что объекты контактов созданы, откройте оснастку "Пользователи и компьютеры" Active Directory и выберите подразделение, в котором эти объекты были созданы. Объекты контактов должны отображаться в области сведений.</span><span class="sxs-lookup"><span data-stu-id="de5b0-p106">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created. The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="de5b0-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="de5b0-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

