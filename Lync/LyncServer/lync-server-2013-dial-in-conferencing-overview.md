---
title: Общие сведения о конференц-связи с телефонным подключением Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 820c880d44a1ecede139a8d3caddf3f6c40e65a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="0043a-102">Общие сведения о конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0043a-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0043a-103">_**Тема последнего изменения:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="0043a-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="0043a-104">Если в вашей организации есть пользователи, которым нужно посетить локальные конференции Lync Server 2013, если они нет на рабочем месте или у них нет доступа к компьютеру, вы можете развернуть Конференц-связь с телефонным подключением, чтобы они могли присоединиться к Конференции с помощью общедоступного коммутируемого телефона сетевой (КТСОП) телефон.</span><span class="sxs-lookup"><span data-stu-id="0043a-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="0043a-105">Конференц-связь с телефонным подключением — это необязательная функция, которую можно настроить при развертывании конференции Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0043a-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="0043a-106">Несмотря на то что в конференц-связи с телефонным подключением используются некоторые компоненты Lync Server 2013, используемые корпоративным голосом, вы можете развернуть Конференц-связь с телефонным подключением, даже если вы не разворачиваете корпоративный голос.</span><span class="sxs-lookup"><span data-stu-id="0043a-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0043a-107">Если вы развертываете Конференц-связь с телефонным подключением, вы должны развернуть ее в каждом пуле, где развертываются конференции Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0043a-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="0043a-108">Вам не нужно назначать номера доступа в каждом пуле, но необходимо развернуть функцию подключения к Интернету в каждом пуле.</span><span class="sxs-lookup"><span data-stu-id="0043a-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="0043a-109">Это требование поддерживает функцию записи имени, когда пользователь вызывает номер доступа из одного пула для присоединения к конференции Lync Server 2013 в другом пуле.</span><span class="sxs-lookup"><span data-stu-id="0043a-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="0043a-110">Для подключений к конференциям в политике собраний должны быть включены конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="0043a-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="0043a-111">По умолчанию приглашение на конференцию с разрешенным телефонным подключением содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0043a-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="0043a-112">НОМЕР цифровой конференции, обозначающий конференцию.</span><span class="sxs-lookup"><span data-stu-id="0043a-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="0043a-113">Один или несколько номеров КОММУТИРУЕМого доступа.</span><span class="sxs-lookup"><span data-stu-id="0043a-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="0043a-114">Ссылка на страницу параметров конференц-связи с телефонным подключением, которая включает полный список номеров доступа со связанными с ними языками; место для создания, сброса и разблокирования персональных идентификационных номеров (ПИН-коды); а также другие сведения, такие как элементы управления двойной частотой с несколькими частотами (DTMF).</span><span class="sxs-lookup"><span data-stu-id="0043a-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="0043a-115">Конференц-связь с телефонным подключением поддерживает как корпоративных, так и анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0043a-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="0043a-116">Корпоративные пользователи имеют учетные данные доменных служб Active Directory и учетные записи Lync Server 2013 в своей организации.</span><span class="sxs-lookup"><span data-stu-id="0043a-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="0043a-117">Анонимным пользователям не назначаются корпоративные учетные данные в организации.</span><span class="sxs-lookup"><span data-stu-id="0043a-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="0043a-118">В ситуации конференц-связи с телефонным подключением пользователь в организации федеративного партнера, подключающийся к конференции по ТСОП, считается анонимным пользователем.</span><span class="sxs-lookup"><span data-stu-id="0043a-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="0043a-119">В отличие от других ситуаций, в конференц-связи с телефонным подключением подлинность федеративных пользователей не проверяется.</span><span class="sxs-lookup"><span data-stu-id="0043a-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="0043a-p105">Корпоративные пользователи или ведущие конференции для присоединения к конференции с разрешенным телефонным доступом набирают один номеров доступа к конференции, после чего им предлагается ввести идентификатор конференции. Если ведущий еще не присоединился к конференции, пользователи могут либо ввести добавочный номер (или полный телефонный номер) в системе объединенных коммуникаций (UC) и PIN‑код, либо дождаться разрешения ведущего. Организатор собрания может присоединиться к собранию в качестве ведущего, введя только PIN‑код. На сервере переднего плана однозначное соответствие между корпоративными пользователями и учетными данными Active Directory устанавливается по сочетанию полного или добавочного телефонного номера номера и PIN‑кода. Таким образом, проверка подлинности и распознавание корпоративных пользователей выполняется по имени в конференции. Корпоративные пользователи могут также взять на себя роль в конференции, предварительно назначенную организатором.</span><span class="sxs-lookup"><span data-stu-id="0043a-p105">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID. If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader. The Meeting organizer can join the meeting as a leader by entering just their PIN. The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials. As a result, enterprise users are authenticated and identified by name in the conference. Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0043a-126">Пользователи предприятий, использующих IP-телефон Office или Lync Server 2013 или Lync 2010, не получают запрос на ввод номера телефона, так как они уже прошли проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0043a-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="0043a-p106">Анонимные пользователи, желающие присоединиться к конференции с телефонным подключением, набирают один из номеров доступа к конференции, а затем у них запрашивается идентификатор конференции. Неавторизованным (не прошедшим проверку подлинности) анонимным пользователям также предлагается записать свое имя. Записанные имена идентифицируют неавторизованных пользователей в конференции. Анонимные пользователи не допускаются в конференцию, пока к ней не присоединится хотя бы один авторизованный пользователь или ведущий, и анонимным пользователям нельзя назначать предопределенную роль.</span><span class="sxs-lookup"><span data-stu-id="0043a-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0043a-p107">Корпоративные пользователи, которые предпочли не указывать свой телефонный номер и ПИН-код, не являются авторизованными. Им предлагается записать имена, и они будут считаться анонимными пользователями в конференции.</span><span class="sxs-lookup"><span data-stu-id="0043a-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="0043a-133">Во время расписания организатор собрания может ограничить доступ к собранию, сделав его закрытым или заблокированным.</span><span class="sxs-lookup"><span data-stu-id="0043a-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="0043a-134">В этом случае при подключении по телефонной линии запрашивается проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="0043a-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="0043a-135">Если пользователи с телефонным подключением не работают или вы не можете проверять подлинность, они переносятся в зал ожидания.</span><span class="sxs-lookup"><span data-stu-id="0043a-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="0043a-136">Они ожидают в зале ожидания, пока они не будут приняты или отклонены, либо они не помещаются в рабочее время и не отключаются друг от друга.</span><span class="sxs-lookup"><span data-stu-id="0043a-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="0043a-137">Пользователи с телефонным подключением прослушивают музыку, если они ожидают, что они могут быть допущены на конференцию.</span><span class="sxs-lookup"><span data-stu-id="0043a-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="0043a-138">После допуска к конференции пользователи, подключающиеся по телефонной линии, могут участвовать в конференции в режиме голосовой связи и выполнять команды двухтонального многочастотного набора (DTMF) с клавиатуры телефона.</span><span class="sxs-lookup"><span data-stu-id="0043a-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="0043a-139">Ведущие конференций с телефонных подключением с помощью команд DTMF разрешают или запрещают пользователям включать и выключать микрофон, блокируют конференцию или снимают ее блокировку, допускают пользователей из "зала ожидания", включают или отключают оповещения о входе и выходе.</span><span class="sxs-lookup"><span data-stu-id="0043a-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="0043a-140">Кроме того, ведущие могут с помощью команды DTMF допустить всех пользователей из "зала ожидания"; при этом права доступа к конференции изменяются: к ней допускаются все присоединяющиеся позднее пользователи.</span><span class="sxs-lookup"><span data-stu-id="0043a-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="0043a-141">Все участники, подключающиеся по телефонной линии, могут с помощью команд DTMF прослушивать справочную информацию и состав участников конференции, а также отключать свои микрофоны.</span><span class="sxs-lookup"><span data-stu-id="0043a-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="0043a-142">Участники телефонного подключения (то есть независимо от того, исключаются ли они абонентами PSTN), могут слышать личные объявления во время конференции, например включить или отключить микрофон, собрание записывается либо кто-то ждет в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="0043a-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0043a-143">Участники, присоединившиеся к конференции не путем набора номера, а путем нажатия на соответствующую ссылку, не слышат персональные уведомления.</span><span class="sxs-lookup"><span data-stu-id="0043a-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

