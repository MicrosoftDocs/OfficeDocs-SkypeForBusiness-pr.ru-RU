---
title: Обзор конференц-связи с телефонным подключением Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d088d07e5d49a916835da581af81ff7def581b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="dfc10-102">Обзор конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfc10-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfc10-103">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="dfc10-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="dfc10-104">Если в Организации есть пользователи, которым необходимо посещать локальные конференции Lync Server 2013, когда они не находятся в офисе или не имеют доступа к компьютеру, можно развернуть Конференц-связь с телефонным подключением, чтобы присоединиться к Конференции с помощью телефонного подключения общего пользования сетевой телефон (PSTN).</span><span class="sxs-lookup"><span data-stu-id="dfc10-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="dfc10-105">Конференц-связь с телефонным подключением это дополнительный компонент, который можно настроить при развертывании конференц-связи Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfc10-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="dfc10-106">Хотя в конференц-связи с телефонным подключением используются некоторые компоненты Lync Server 2013, используемые корпоративной голосовой связью, вы можете развернуть Конференц-связь с телефонным подключением даже в том случае, если вы не развертываете корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="dfc10-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfc10-107">Если вы развертываете Конференц-связь с телефонным подключением, необходимо развернуть ее в каждом пуле, где развертывается Конференц-связь Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfc10-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="dfc10-108">Назначать номера доступа в каждом пуле не обязательно, но функция конференц-связи с телефонным подключением должна быть развернута в каждом пуле.</span><span class="sxs-lookup"><span data-stu-id="dfc10-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="dfc10-109">Это требование поддерживает функцию записи имени, когда пользователь вызывает номер доступа из одного пула для присоединения к конференции Lync Server 2013 в другом пуле.</span><span class="sxs-lookup"><span data-stu-id="dfc10-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="dfc10-p103">Должен быть разрешен телефонный доступ к конференциям в политике собраний. По умолчанию приглашение на конференцию с разрешенным телефонным подключением содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dfc10-p103">Conferences must be enabled for dial-in access in meeting policy. By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="dfc10-112">числовой идентификатор конференции, который определяет конференцию;</span><span class="sxs-lookup"><span data-stu-id="dfc10-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="dfc10-113">хотя бы один номер доступа ТСОП;</span><span class="sxs-lookup"><span data-stu-id="dfc10-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="dfc10-114">Ссылка на страницу параметров конференц-связи с телефонным подключением, которая содержит полный список номеров доступа со связанными с ними языками; место для создания, сброса или разблокирования персональных идентификационных номеров (ПИН-кодов); и другие сведения, такие как элементы управления сдвоенной многочастотной (DTMF).</span><span class="sxs-lookup"><span data-stu-id="dfc10-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="dfc10-115">Конференц-связь с телефонным подключением поддерживает как корпоративных, так и анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="dfc10-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="dfc10-116">Корпоративные пользователи имеют учетные данные доменных служб Active Directory и учетные записи Lync Server 2013 в своей организации.</span><span class="sxs-lookup"><span data-stu-id="dfc10-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="dfc10-117">Анонимные пользователи не имеют корпоративных учетных данных в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dfc10-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="dfc10-118">В контексте конференц-связи с телефонным подключением пользователь в организации федеративного партнера, использующий ТСОП для присоединения к конференции, считается анонимным пользователем.</span><span class="sxs-lookup"><span data-stu-id="dfc10-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="dfc10-119">В отличие от других контекстов, в конференц-связи с телефонным подключением проверка подлинности федеративных пользователей не выполняется.</span><span class="sxs-lookup"><span data-stu-id="dfc10-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="dfc10-120">Корпоративные пользователи или ведущие конференции для присоединения к конференции с разрешенным телефонным доступом набирают один номеров доступа к конференции, а затем им предлагается ввести идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="dfc10-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="dfc10-121">Если ведущий еще не присоединился к конференции, то пользователи могут либо ввести свой добавочный номер в системе объединенных коммуникаций (или полный телефонный номер) и ПИН-код, либо подождать, пока ведущий не допустит их в конференцию.</span><span class="sxs-lookup"><span data-stu-id="dfc10-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="dfc10-122">Организаторы собрания могут присоединяться к собранию как ведущие, введя только свой ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="dfc10-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="dfc10-123">Сервер переднего плана использует сочетание полного номера телефона, добавочного номера и ПИН-кода для уникальной связи корпоративных пользователей с их учетными данными Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dfc10-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="dfc10-124">В результате выполняется проверка подлинности и идентификация корпоративных пользователей по имени в конференции.</span><span class="sxs-lookup"><span data-stu-id="dfc10-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="dfc10-125">Корпоративные пользователи могут также взять на себя роль в конференции, предопределенную организатором.</span><span class="sxs-lookup"><span data-stu-id="dfc10-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfc10-126">Для корпоративных пользователей, исходящих через IP-телефон Office или из Lync Server 2013 или Lync 2010, не запрашиваются номера телефонов, так как они уже прошли проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="dfc10-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="dfc10-p106">Анонимные пользователи, желающие присоединиться к конференции с телефонным подключением, набирают один из номеров доступа к конференции, а затем у них запрашивается идентификатор конференции. Неавторизованным (не прошедшим проверку подлинности) анонимным пользователям также предлагается записать свое имя. Записанные имена идентифицируют неавторизованных пользователей в конференции. Анонимные пользователи не допускаются в конференцию, пока к ней не присоединится хотя бы один авторизованный пользователь или ведущий, и анонимным пользователям нельзя назначать предопределенную роль.</span><span class="sxs-lookup"><span data-stu-id="dfc10-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfc10-p107">Корпоративные пользователи, которые предпочли не указывать свой телефонный номер и ПИН-код, не являются авторизованными. Им предлагается записать имена, и они будут считаться анонимными пользователями в конференции.</span><span class="sxs-lookup"><span data-stu-id="dfc10-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="dfc10-p108">Во время составления расписания организатор собрания может решить ограничить доступ к собранию, сделав его закрытым или заблокированным. В таком случае пользователям с телефонным подключением будет предлагаться пройти проверку подлинности. Если проверка подлинности завершается неудачно, или если пользователи отказываются ее пройти, то такие пользователи перемещаются в "зал ожидания", где ожидают, пока ведущий не решит, принять или отклонить их заявку на участие, или пока срок ожидания не истечет, и они не будут отключены. Пока пользователи с телефонным подключением ожидают решение о допуске к конференции, они прослушивают музыку. После допуска к конференции пользователи с телефонным подключением могут принимать участие в звуковой части конференции и выполнять команды двухтонального многочастотного набора (DTMF) с помощью клавиатуры телефона. Ведущие, подключившиеся к конференции по телефону, могут выполнять команды DTMF, чтобы позволить участникам включать и отключать микрофон, чтобы блокировать и разблокировать конференцию, допускать пользователей из "зала ожидания", а также включать и отключать уведомления о входе и выходе. Ведущие могут также использовать команды DTMF, чтобы допускать всех пользователей из "зала ожидания", в результате чего разрешения собрания изменяются, и к собранию будут допускаться все, кто впоследствии присоединяется. Все участники с телефонным подключением могут использовать команды DTMF, чтобы прослушивать справку или реестр конференции, а также выключать свой звук.</span><span class="sxs-lookup"><span data-stu-id="dfc10-p108">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked. In this case, dial-in users are requested to authenticate. If dial-in users fail or choose not to authenticate, they are transferred to the lobby. They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected. Dial-in users hear music if they are waiting to be admitted to the conference. After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad. Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off. Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins. All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="dfc10-142">Участники с телефонным подключением (как присоединившиеся из ТСОП, так и другие) прослушивают во время конференции персональные уведомления, например о том, что их звук выключен или включен, что собрание записывается, или что кто-то ожидает в "зале ожидания".</span><span class="sxs-lookup"><span data-stu-id="dfc10-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfc10-143">Участники, присоединившиеся к конференции не путем набора номера, а путем нажатия на соответствующую ссылку, не слышат персональные уведомления.</span><span class="sxs-lookup"><span data-stu-id="dfc10-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

