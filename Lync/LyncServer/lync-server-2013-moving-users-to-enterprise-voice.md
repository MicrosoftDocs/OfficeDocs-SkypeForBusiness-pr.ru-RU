---
title: 'Lync Server 2013: перемещение пользователей на корпоративную голосовую связь'
description: 'Lync Server 2013: перемещение пользователей на корпоративную голосовую связь.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b075f916f4d81d8d3c24c24c7393be58e10a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542015"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="de4d5-103">Перемещение пользователей на корпоративную голосовую связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de4d5-103">Moving users to Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de4d5-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="de4d5-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="de4d5-105">Если вы перемещаете пользователей из существующей инфраструктуры телефонной сети УАТС в корпоративную голосовую связь, процесс развертывания включает некоторые действия, которые не входят в процесс планирования, описанный в статье [планирование использования корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="de4d5-105">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="de4d5-106">Сведения о переносе пользователей из предыдущего развертывания корпоративной голосовой связи можно найти в документе миграции, которые были включены в установочный носитель.</span><span class="sxs-lookup"><span data-stu-id="de4d5-106">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="de4d5-107">Процесс перемещения пользователей из существующей инфраструктуры телефонии в корпоративную голосовой связи состоит из следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="de4d5-107">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="de4d5-108">Назначение основных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="de4d5-108">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="de4d5-109">активируйте пользователей для применения Enterprise Voice;</span><span class="sxs-lookup"><span data-stu-id="de4d5-109">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="de4d5-110">Подготовка абонентских групп для пользователей.</span><span class="sxs-lookup"><span data-stu-id="de4d5-110">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="de4d5-111">Планирование политик голосовых служб на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="de4d5-111">Plan user voice policies.</span></span>

5.  <span data-ttu-id="de4d5-112">Планирование маршрутов звонков.</span><span class="sxs-lookup"><span data-stu-id="de4d5-112">Plan call routes.</span></span>

6.  <span data-ttu-id="de4d5-113">Настройка магистрали УАТС или SIP для перенаправления звонков пользователям, включенным для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="de4d5-113">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="de4d5-114">Перемещение пользователей в единую систему обмена сообщениями Exchange (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="de4d5-114">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="de4d5-115">В этом разделе описываются этапы планирования, требуемые для каждого шага.</span><span class="sxs-lookup"><span data-stu-id="de4d5-115">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="de4d5-p102">Шаг 1. Назначение основных номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="de4d5-p102">Step 1. Designate primary phone numbers</span></span>

<span data-ttu-id="de4d5-118">Корпоративная голосовая связь интегрирует голосовой связи с другими носителями обмена сообщениями, например, когда входящий вызов поступает на сервер, сервер сопоставляет номер с идентификатором SIP URI пользователя, а затем разделяет вызов на все конечные точки клиента, связанные с этим ИДЕНТИФИКАТОРом SIP.</span><span class="sxs-lookup"><span data-stu-id="de4d5-118">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="de4d5-119">Этот процесс требует, чтобы каждый пользователь был связан с основным номером телефона.</span><span class="sxs-lookup"><span data-stu-id="de4d5-119">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="de4d5-120">Основной номер телефона должен обладать следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="de4d5-120">A primary phone number must be:</span></span>

  - <span data-ttu-id="de4d5-121">Номер должен быть глобальным и уникальным, а если номер является внутренним добавочным номером, то он должен быть уникальным в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="de4d5-121">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="de4d5-p104">Номер должен принадлежать организации и поддерживать маршрутизацию. Не допускается использование личных номеров.</span><span class="sxs-lookup"><span data-stu-id="de4d5-p104">Owned by and routable in the enterprise. Personal numbers should not be used.</span></span>

<span data-ttu-id="de4d5-124">В доменных службах Active Directory для корпоративных пользователей могут быть указаны два или более номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="de4d5-124">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="de4d5-125">Для просмотра или изменения номеров телефонов, связанных с конкретным пользователем, можно использовать таблицу свойств в оснастке "Пользователи и компьютеры" Active Directory.</span><span class="sxs-lookup"><span data-stu-id="de4d5-125">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="de4d5-p106">В поле **Telephone number** (Номер телефона) вкладки **General** (Общие) диалогового окна **User Properties** (Свойства пользователя) должен содержаться основной рабочий номер телефона пользователя. Этот номер обычно назначается в качестве основного номера телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="de4d5-p106">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number. This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="de4d5-128">Некоторым пользователям могут потребоваться дополнительные возможности. Например, руководителю может потребоваться перенаправлять все входящие звонки через помощника. Однако подобные исключения должны касаться только тех случаев, когда потребность является прозрачной и критически важной.</span><span class="sxs-lookup"><span data-stu-id="de4d5-128">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="de4d5-129">Выбранный основной номер должен:</span><span class="sxs-lookup"><span data-stu-id="de4d5-129">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="de4d5-130">Номер должен быть преобразован в формат E.164, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="de4d5-130">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="de4d5-131">Номер должен быть скопирован в атрибут Active Directory **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="de4d5-131">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="de4d5-132"><STRONG>Совместное использование корпоративной голосовой связи с функцией удаленного управления звонками (RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="de4d5-132"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="de4d5-133">RCC — это возможность использовать Lync Server для мониторинга и управления телефонной УАТС для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="de4d5-133">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="de4d5-134">Управление осуществляется через сервер, который выступает в роли шлюза УАТС.</span><span class="sxs-lookup"><span data-stu-id="de4d5-134">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="de4d5-135">Несмотря на то, что вы не можете настроить для пользователя как по протоколу RCC, так и для корпоративной голосовой связи, параметр URI линии определяет основной номер телефона пользователя в любом случае.</span><span class="sxs-lookup"><span data-stu-id="de4d5-135">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="de4d5-136">Если у вас уже есть инфраструктура УАТС, которую вы хотите использовать для работы с пользователями, вы можете получить корпоративную голосовую связь в Организации.</span><span class="sxs-lookup"><span data-stu-id="de4d5-136">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="de4d5-137">Для получения дополнительных сведений об этом сценарии развертывания обратитесь к разделу <A href="lync-server-2013-direct-sip-deployment-options.md">Параметры прямого развертывания SIP в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="de4d5-137">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="de4d5-138">В предыдущих выпусках вы можете включить как RCC, так и корпоративную голосовую связь для пользователя, но только в том случае, если вы также настроили для пользователя двойное ветвление, возможность, при которой входящий вызов будет звонить на телефон УАТС пользователя и Communicator одновременно.</span><span class="sxs-lookup"><span data-stu-id="de4d5-138">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="de4d5-139">В Lync Server 2010 не поддерживается двойное ветвление.</span><span class="sxs-lookup"><span data-stu-id="de4d5-139">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="de4d5-140">Существует 3 способа указания значения атрибута **msRTCSIP-line**:</span><span class="sxs-lookup"><span data-stu-id="de4d5-140">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="de4d5-141">Microsoft Identity Integration Server (рекомендуемый способ)</span><span class="sxs-lookup"><span data-stu-id="de4d5-141">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="de4d5-142">Страница " **Пользователи** " в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="de4d5-142">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="de4d5-p110">Для обработки большого числа номеров телефонов рекомендуется использовать пользовательский скрипт, разработанный в организации. В зависимости от способа, используемого организацией для представления номеров телефонов в доменных службах Active Directory, может потребоваться преобразовывать основные номера телефонов в формат E.164 перед копированием в атрибут **msRTCSIP-line** с помощью сценария.</span><span class="sxs-lookup"><span data-stu-id="de4d5-p110">Where many phone numbers must be processed, a script custom developed by your organization is the better choice. Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="de4d5-145">Если для хранения всех номеров телефонов организации в доменных службах Active Directory используется единый формат E.164, сценарию потребуется только записать каждый основной номер телефона в атрибут **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="de4d5-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="de4d5-146">Если для хранения всех номеров телефонов организации в доменных службах Active Directory используется единый формат, отличный от E.164, то сценарию потребуется определить соответствующее правило нормализации для преобразования основных номеров телефонов в формат E.164 перед записью номеров в атрибут **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="de4d5-146">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="de4d5-147">Если для хранения номеров телефонов организации в доменных службах Active Directory используются нестандартные форматы, то сценарию потребуется определить соответствующее правило нормализации для преобразования основных номеров телефонов из различных форматов в формат E.164 перед записью номеров в атрибут **msRTCSIP-line**.</span><span class="sxs-lookup"><span data-stu-id="de4d5-147">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="de4d5-148">Кроме того, перед записью в атрибут **msRTCSIP-line** сценарий должен добавлять префикс **Tel:** перед каждым основным номером телефона.</span><span class="sxs-lookup"><span data-stu-id="de4d5-148">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="de4d5-149">Ожидаемый формат номера телефона, указанный в этом атрибуте:</span><span class="sxs-lookup"><span data-stu-id="de4d5-149">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="de4d5-150">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="de4d5-150">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="de4d5-151">Tel:5550100 (для добавочных номеров, уникальных в пределах организации)</span><span class="sxs-lookup"><span data-stu-id="de4d5-151">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="de4d5-152">Нормализация, выполняемая службой адресной книги, не исключает необходимость нормализации основного номера телефона каждого пользователя в доменных службах Active Directory, поскольку служба адресной книги не имеет доступа к доменным службам Active Directory и, следовательно, не может копировать основные номера телефонов в атрибут <STRONG> msRTCSIP-Line </STRONG>.</span><span class="sxs-lookup"><span data-stu-id="de4d5-152">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="de4d5-p111">Шаг 2. Включение пользователей для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="de4d5-p111">Step 2. Enable users for Enterprise Voice</span></span>

<span data-ttu-id="de4d5-155">Для выполнения этого шага достаточно определить список пользователей, которых необходимо включить для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="de4d5-155">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="de4d5-p112">Шаг 3. Подготовка абонентских групп для пользователей.</span><span class="sxs-lookup"><span data-stu-id="de4d5-p112">Step 3. Prepare dial plans for users.</span></span>

<span data-ttu-id="de4d5-158">Пользователи, для которых включена поддержка корпоративной голосовой связи, не смогут совершать звонки в PSTN без абонентских абонентов.</span><span class="sxs-lookup"><span data-stu-id="de4d5-158">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="de4d5-159">Абонентская группа — это именованный набор правил нормализации, которые преобразуют номера телефонов для расположения, отдельного пользователя или контактного объекта в единый стандартный формат (E.164) для авторизации телефонов и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="de4d5-159">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="de4d5-160">Правила нормализации определяют, как номера телефонов, заданные в различных форматах, перенаправляются в требуемое расположение, требуемому пользователю или контактному объекту.</span><span class="sxs-lookup"><span data-stu-id="de4d5-160">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="de4d5-161">Сведения о подготовке абонентских абонентов приведены [в статье абонентские группы и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="de4d5-161">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="de4d5-162">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="de4d5-162">Step 4.</span></span> <span data-ttu-id="de4d5-163">Планирование политик голосовых служб на уровне пользователей</span><span class="sxs-lookup"><span data-stu-id="de4d5-163">Plan user voice policies</span></span>

<span data-ttu-id="de4d5-164">Пользовательские параметры класса услуг, используемые в устаревших УАТС, например право на междугороднюю или международную связь с использованием телефонов организации, должны быть заданы с помощью политик VoIP.</span><span class="sxs-lookup"><span data-stu-id="de4d5-164">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="de4d5-165">Сведения о планировании и создании политик для корпоративной голосовой связи можно найти [в статье политики голосовой связи в Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="de4d5-165">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="de4d5-166">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="de4d5-166">Step 5.</span></span> <span data-ttu-id="de4d5-167">Планирование маршрутов исходящих звонков</span><span class="sxs-lookup"><span data-stu-id="de4d5-167">Plan outbound call routes</span></span>

<span data-ttu-id="de4d5-168">Маршруты вызовов определяют, как Lync Server обрабатывает исходящие вызовы, размещаемые пользователями корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="de4d5-168">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="de4d5-169">Сервер преобразует номер, набираемый пользователем, в формат E.164 при необходимости и пытается сопоставить его с SIP URI.</span><span class="sxs-lookup"><span data-stu-id="de4d5-169">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="de4d5-170">Если серверу не удается найти соответствие, он применяет к исходящему звонку логику маршрутизации на основании номера.</span><span class="sxs-lookup"><span data-stu-id="de4d5-170">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="de4d5-171">Завершающим шагом в определении этой логики является создание отдельного именованного маршрута звонка для каждого набора конечных номеров телефона, указанных в абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="de4d5-171">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="de4d5-172">Более подробную информацию о планировании маршрутов звонков можно узнать [в статье Route Voices in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="de4d5-172">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="de4d5-173">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="de4d5-173">Step 6.</span></span> <span data-ttu-id="de4d5-174">Настройка магистрали УАТС или SIP для перенаправления звонков пользователям, включенным для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="de4d5-174">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="de4d5-175">Пользователи, которые ранее были расположены на традиционных УАТС или использовали подключение SIP к поставщику услуг телефонии и Интернета, сохранят свои номера после перемещения.</span><span class="sxs-lookup"><span data-stu-id="de4d5-175">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="de4d5-176">Единственное требование состоит в том, что после перемещения УАТС или магистральная линия SIP необходимо настроить на маршрутизацию входящих вызовов для пользователей корпоративной голосовой связи на сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="de4d5-176">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="de4d5-p120">Шаг 7. Перемещение пользователей в единую систему обмена сообщениями Exchange (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="de4d5-p120">Step 7. Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="de4d5-179">Для перемещения пользователей в единую систему обмена сообщениями Exchange необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="de4d5-179">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="de4d5-180">Настройте единую систему обмена сообщениями Exchange и Lync Server для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="de4d5-180">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="de4d5-181">Включите пользователей для ответа на звонки единой системы обмена сообщениями Exchange и голосового доступа к Outlook.</span><span class="sxs-lookup"><span data-stu-id="de4d5-181">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="de4d5-182">Это действие выполняется на сервере единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="de4d5-182">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="de4d5-183">Подробные сведения можно найти в статье Exchange Server 2010 Library TechNet по адресу [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) .</span><span class="sxs-lookup"><span data-stu-id="de4d5-183">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

