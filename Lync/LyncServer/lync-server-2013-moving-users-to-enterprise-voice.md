---
title: 'Lync Server 2013: перемещение пользователей на корпоративную голосовую связь'
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
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="e2faf-102">Перемещение пользователей на корпоративную голосовую связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2faf-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2faf-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e2faf-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e2faf-104">Если вы перемещаете пользователей из существующей инфраструктуры телефонной АТС в корпоративную, процесс развертывания включает некоторые действия, которые не входят в процесс планирования, описанный в разделе [планирование для корпоративного голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="e2faf-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="e2faf-105">Сведения о переносе пользователей из более ранней версии корпоративного выпуска можно найти в документах о миграции, которые были включены в установочный носитель.</span><span class="sxs-lookup"><span data-stu-id="e2faf-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="e2faf-106">Процесс перемещения пользователей из существующей инфраструктуры телефонии в корпоративный голос состоит из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="e2faf-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="e2faf-107">Назначение основного номера телефона.</span><span class="sxs-lookup"><span data-stu-id="e2faf-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="e2faf-108">активируйте корпоративную голосовую связь для пользователей;</span><span class="sxs-lookup"><span data-stu-id="e2faf-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="e2faf-109">Подготовка абонентской группы для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2faf-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="e2faf-110">Планирование политик голосовой связи для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2faf-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="e2faf-111">Планирование маршрутов звонков.</span><span class="sxs-lookup"><span data-stu-id="e2faf-111">Plan call routes.</span></span>

6.  <span data-ttu-id="e2faf-112">Настройка магистральной магистрали или канала SIP для переадресации звонков для пользователей, для которых включена Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="e2faf-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="e2faf-113">Перемещение пользователей в единую систему обмена сообщениями (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="e2faf-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="e2faf-114">В этой статье описывается планирование, необходимое для каждого из этих шагов.</span><span class="sxs-lookup"><span data-stu-id="e2faf-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="e2faf-115">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="e2faf-115">Step 1.</span></span> <span data-ttu-id="e2faf-116">Назначение основного номера телефона</span><span class="sxs-lookup"><span data-stu-id="e2faf-116">Designate primary phone numbers</span></span>

<span data-ttu-id="e2faf-117">Корпоративная голосовая связь интегрирует голосовой связи с другими мультимедийными данными, например при поступлении входящего звонка на сервер, сервер сопоставляет номер с идентификатором SIP URI пользователя, а затем разделяет вызов на все конечные точки клиента, связанные с этим SIP (URI).</span><span class="sxs-lookup"><span data-stu-id="e2faf-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="e2faf-118">Этот процесс требует, чтобы каждый пользователь был связан с основным номером телефона.</span><span class="sxs-lookup"><span data-stu-id="e2faf-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="e2faf-119">Основной номер телефона должен быть:</span><span class="sxs-lookup"><span data-stu-id="e2faf-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="e2faf-120">Глобально уникальным образом или, в случае внутренних расширений, уникален в масштабах предприятия.</span><span class="sxs-lookup"><span data-stu-id="e2faf-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="e2faf-121">Владелец и маршрутизация в масштабах предприятия.</span><span class="sxs-lookup"><span data-stu-id="e2faf-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="e2faf-122">Личные номера не следует использовать.</span><span class="sxs-lookup"><span data-stu-id="e2faf-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="e2faf-123">В доменных службах Active Directory для корпоративных пользователей могут быть указаны несколько номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="e2faf-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="e2faf-124">Все телефонные номера, связанные с определенным пользователем, можно просмотреть или изменить на странице свойств для этого пользователя в оснастке "пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="e2faf-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="e2faf-125">Поле « **номер телефона** » на вкладке « **Общие** » диалогового окна « **Свойства пользователя** » должно содержать основной рабочий номер пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2faf-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="e2faf-126">Этот номер обычно назначается в качестве основного номера телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2faf-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="e2faf-127">Некоторые пользователи могут иметь особые требования (например, руководителя, который хочет получать все входящие звонки, направляемые через помощник администратора), но такие исключения должны быть ограничены только теми, в которых нужна необходимость очистки и критической ошибки.</span><span class="sxs-lookup"><span data-stu-id="e2faf-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="e2faf-128">После выбора основного номера необходимо:</span><span class="sxs-lookup"><span data-stu-id="e2faf-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="e2faf-129">По возможности нормализованы на формат E. 164, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="e2faf-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="e2faf-130">Копируется в атрибут Active Directory **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="e2faf-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2faf-131"><STRONG>Совместное с удаленным управлением вызовом (RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="e2faf-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="e2faf-132">RCC — это возможность использовать Lync Server для мониторинга и управления настольными телефонами АТС.</span><span class="sxs-lookup"><span data-stu-id="e2faf-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="e2faf-133">Управление передается через сервер, который выступает в качестве шлюза для УАТС.</span><span class="sxs-lookup"><span data-stu-id="e2faf-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="e2faf-134">Несмотря на то, что вы не можете настроить пользователя как для RCC, так и для корпоративной голосовой связи, параметр универсального кода ресурса (URI) Line задает основной номер телефона пользователя в любом случае.</span><span class="sxs-lookup"><span data-stu-id="e2faf-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="e2faf-135">Если вы хотите, чтобы выбранные пользователи продолжали использовать инфраструктуру УАТС, вы можете последовательно добавить корпоративный голос в организацию.</span><span class="sxs-lookup"><span data-stu-id="e2faf-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="e2faf-136">Подробнее об этом сценарии развертывания можно найти <A href="lync-server-2013-direct-sip-deployment-options.md">в разделе Параметры развертывания Direct SIP в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e2faf-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="e2faf-137">В предыдущих выпусках вы можете включить как RCC, так и корпоративную голосовую почту для пользователя, но только в том случае, если вы также настроили пользователя для двойного разветвления, то есть функции, из-за которой входящий звонок будет звонить на стационарные телефоны пользователей и Communicator одновременно.</span><span class="sxs-lookup"><span data-stu-id="e2faf-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="e2faf-138">В Lync Server 2010 функция двойного разветвления не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e2faf-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="e2faf-139">Для заполнения атрибута **msRTCSIP-Line** есть три метода:</span><span class="sxs-lookup"><span data-stu-id="e2faf-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="e2faf-140">Сервер Microsoft Identity Integration Server (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="e2faf-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="e2faf-141">Страница " **Пользователи** " на панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="e2faf-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="e2faf-142">Если необходимо обработать несколько номеров телефонов, лучшим вариантом является сценарий, разработанный разработчиком.</span><span class="sxs-lookup"><span data-stu-id="e2faf-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="e2faf-143">В зависимости от того, как ваша организация представляет номера телефонов в доменных службах Active Directory, может потребоваться нормализация основных телефонных номеров в формат E. 164 перед копированием их в атрибут **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="e2faf-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="e2faf-144">Если ваша организация хранит все телефонные номера в доменных службах Active Directory в одном формате, а формат "E. 164", ваш сценарий должен записывать каждый основной телефонный номер в атрибут **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="e2faf-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="e2faf-145">Если ваша организация хранит все телефонные номера в доменных службах Active Directory в едином формате, но этот формат отличается от E. 164, ваш сценарий должен определить соответствующее правило нормализации, чтобы преобразовать основные телефонные номера из существующего формата в формат E. 164, прежде чем записать их в атрибут **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="e2faf-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="e2faf-146">Если в вашей организации не используется стандартный формат телефонных номеров в доменных службах Active Directory, ваш сценарий должен определить соответствующие правила нормализации, чтобы преобразовать основные номера телефонов в формат E. 164 для соответствия требованиям, прежде чем заставлять основные номера телефонов в атрибут **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="e2faf-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="e2faf-147">Кроме того, ваш сценарий должен вставить префикс **Tel:** перед записью в атрибут **msRTCSIP-Line** .</span><span class="sxs-lookup"><span data-stu-id="e2faf-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="e2faf-148">Ожидаемый формат числа, указанного в этом атрибуте:</span><span class="sxs-lookup"><span data-stu-id="e2faf-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="e2faf-149">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="e2faf-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="e2faf-150">Tel: 5550100 (для уникальных глобальных расширений для предприятий)</span><span class="sxs-lookup"><span data-stu-id="e2faf-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e2faf-151">Нормализация, выполненная службой адресной книги (ABS), не заменяет или, в противном случае, исключает необходимость нормализации основного номера каждого пользователя в доменных службах Active Directory, так как она не имеет доступа к доменным службам Active Directory, поэтому не может копировать первичные номера в атрибут <STRONG>msRTCSIP-Line</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e2faf-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="e2faf-152">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="e2faf-152">Step 2.</span></span> <span data-ttu-id="e2faf-153">Включение пользователей для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="e2faf-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="e2faf-154">Кроме того, чтобы определить, какие пользователи будут включены, для выполнения этого действия не требуется специального планирования.</span><span class="sxs-lookup"><span data-stu-id="e2faf-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="e2faf-155">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="e2faf-155">Step 3.</span></span> <span data-ttu-id="e2faf-156">Подготовка абонентской группы для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2faf-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="e2faf-157">Пользователи, которым разрешена поддержка корпоративной голосовой связи, не смогут звонить в сеть PSTN без абонентов.</span><span class="sxs-lookup"><span data-stu-id="e2faf-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="e2faf-158">Абонентская группа — это именованный набор правил нормализации, которые преобразуют номера телефонов для именованного расположения, отдельного пользователя или контактного объекта в единый стандартный формат (E.164) для авторизации телефонов и маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="e2faf-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="e2faf-159">Правила нормализации определяют, как номера телефонов, заданные в различных форматах, перенаправляются в требуемое расположение, требуемому пользователю или контактному объекту.</span><span class="sxs-lookup"><span data-stu-id="e2faf-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="e2faf-160">Сведения о подготовке абонентов можно найти в статьях [абонентские группы и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="e2faf-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="e2faf-161">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="e2faf-161">Step 4.</span></span> <span data-ttu-id="e2faf-162">Планирование политик голосовой связи для пользователей</span><span class="sxs-lookup"><span data-stu-id="e2faf-162">Plan user voice policies</span></span>

<span data-ttu-id="e2faf-163">Параметры классического обслуживания пользователей для старой АТС, такие как право на междугородние и международные звонки с телефонов компаний, должны быть настроены в соответствии с настройками политик VoIP для пользователей, перемещенных в корпоративный голос.</span><span class="sxs-lookup"><span data-stu-id="e2faf-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="e2faf-164">Подробные сведения о планировании и создании политик для корпоративной голосовой почты можно найти [в разделе политики голосовой связи в Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e2faf-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="e2faf-165">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="e2faf-165">Step 5.</span></span> <span data-ttu-id="e2faf-166">Планирование маршрутов исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="e2faf-166">Plan outbound call routes</span></span>

<span data-ttu-id="e2faf-167">Маршруты звонков определяют, как Lync Server обрабатывает исходящие звонки, размещенные пользователями корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e2faf-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="e2faf-168">Когда пользователь набирает номер, сервер (при необходимости) нормализует строку набора номера на формат E. 164 и пытается сопоставить ее с URI SIP.</span><span class="sxs-lookup"><span data-stu-id="e2faf-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="e2faf-169">Если сервер не может установить соответствие, он применяет логику маршрутизации исходящих вызовов на основе числа.</span><span class="sxs-lookup"><span data-stu-id="e2faf-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="e2faf-170">Последний шаг в определении того, что логика создает отдельный маршрут вызова для каждого набора телефонных номеров, указанных в каждой абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="e2faf-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="e2faf-171">Дополнительные сведения о планировании маршрутов звонков можно найти [в разделе маршруты к голосовой связи в Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="e2faf-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="e2faf-172">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="e2faf-172">Step 6.</span></span> <span data-ttu-id="e2faf-173">Настройка магистральной магистрали или канала SIP для переадресации звонков для пользователей корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="e2faf-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="e2faf-174">Пользователи, которые ранее были размещены на обычной АТС или на магистральном подключении по каналу SIP с поставщиком услуг телефонной связи через Интернет (ИТСП), сохраняют номера своих телефонов после перемещения.</span><span class="sxs-lookup"><span data-stu-id="e2faf-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="e2faf-175">Единственным требованием является то, что после перемещения необходимо перенастроить магистраль УАТС или SIP для маршрутизации входящих звонков для пользователей корпоративной голосовой связи на сервер обновлений.</span><span class="sxs-lookup"><span data-stu-id="e2faf-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="e2faf-176">Шаг 7.</span><span class="sxs-lookup"><span data-stu-id="e2faf-176">Step 7.</span></span> <span data-ttu-id="e2faf-177">Перемещение пользователей в единую систему обмена сообщениями (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="e2faf-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="e2faf-178">Перемещение пользователей в единую систему обмена сообщениями включает следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="e2faf-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="e2faf-179">Настройте единую систему обмена сообщениями Exchange и Lync Server для совместной работы.</span><span class="sxs-lookup"><span data-stu-id="e2faf-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="e2faf-180">Разрешить пользователям отвечать на звонки через единую систему обмена сообщениями Exchange и голосовой доступ к Outlook.</span><span class="sxs-lookup"><span data-stu-id="e2faf-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="e2faf-181">Эта задача выполняется на сервере единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="e2faf-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="e2faf-182">Подробные сведения можно найти в библиотеке TechNet Server 2010 [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span><span class="sxs-lookup"><span data-stu-id="e2faf-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

