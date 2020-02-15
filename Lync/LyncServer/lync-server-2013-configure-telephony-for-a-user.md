---
title: 'Lync Server 2013: Настройка телефонии для пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cac7f13d7ba46b9affee1f4d44dd56b167597b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="a3ffc-102">Настройка телефонии для пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3ffc-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3ffc-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a3ffc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a3ffc-104">Параметры телефонии — это некоторые индивидуальные параметры учетной записи пользователя, которые можно настроить в панели управления Lync Server для пользователя (то есть, если отдельный пользователь включен для Lync Server 2013 и организация поддерживает телефонию).</span><span class="sxs-lookup"><span data-stu-id="a3ffc-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="a3ffc-105">Параметры телефонии пользователей Lync Server включают следующие:</span><span class="sxs-lookup"><span data-stu-id="a3ffc-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="a3ffc-106">**Звук и видео отключены**   . пользователь не может совершать вызовы с помощью аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="a3ffc-107">**PC to PC только**   пользователь может выполнять аудио и видеозвонки только между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="a3ffc-108">**Корпоративная голосовая связь**   пользователь может использовать инфраструктуру Lync Server 2013 для маршрутизации всех входящих и исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="a3ffc-109">Пользователь также может выполнять вызовы с компьютера на компьютер.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="a3ffc-110">**Удаленное управление**   звонками пользователь может использовать Lync Server 2013 для управления настольным телефоном, а также выполнять звонки между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="a3ffc-111">Подробнее о настройке телефонии для организации можно узнать в статье [Настройка телефонии для пользователя в Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) и [Развертывание корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="a3ffc-112">Настройка телефонии для конкретной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="a3ffc-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="a3ffc-113">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a3ffc-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a3ffc-115">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a3ffc-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a3ffc-116">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a3ffc-117">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, которая требуется, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="a3ffc-118">В таблице щелкните учетную запись пользователя, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="a3ffc-119">В меню **Правка** щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="a3ffc-120">В разделе **Телефония** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a3ffc-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="a3ffc-121">Чтобы отключить аудио- и видеовызовы для пользователя, щелкните **Аудио/видео отключено**.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="a3ffc-p103">Чтобы включить аудиосвязь с компьютера на компьютер для пользователя, но при этом не включать удаленное управление вызовами или корпоративную голосовую связь, щелкните **Только с ПК на ПК**. Укажите значение для идентификатора \*\*Линейный URI \*\* для телефона, который пользователь использует для выполнения аудиовызовов с компьютера на компьютер.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="a3ffc-124">Чтобы перенаправить телефонные звонки пользователя с помощью инфраструктуры Lync Server 2010 в соответствии с классом политики службы, включая голосовую связь между ПК и ПК, нажмите **Корпоративная Голосовая**связь.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="a3ffc-125">В поле **Линейный URI** укажите номер телефона для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="a3ffc-126">В полях **Политика абонентских групп** и **Политика голосовой связи** укажите соответствующие политики для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="a3ffc-127">Чтобы указать правила нормализации для преобразования номеров телефона, набираемых пользователем, в формат E.164, выберите соответствующий профиль местоположения в разделе **Политика определения местоположения**.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="a3ffc-128">Чтобы включить удаленное управление звонками, которое позволяет пользователям управлять телефонной линии рабочего стола из Lync Server 2013 для совершения вызовов между компьютерами и телефонными звонками, щелкните **Удаленное управление звонками**.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="a3ffc-129">В поле **Линейный URI** укажите номер телефона для удаленного управления вызовами.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="a3ffc-130">Для маршрутизации вызовов пользователю требуется настольный телефон и подключение к системе PBX.</span><span class="sxs-lookup"><span data-stu-id="a3ffc-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a3ffc-131">См. также</span><span class="sxs-lookup"><span data-stu-id="a3ffc-131">See Also</span></span>


[<span data-ttu-id="a3ffc-132">Изменение свойств учетной записи пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3ffc-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

