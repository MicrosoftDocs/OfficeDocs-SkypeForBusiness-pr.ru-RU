---
title: 'Lync Server 2013: создание или изменение общедоступных федеративных поставщиков SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58b0ffdc009d48ef82d1bdf3ba8662cd4072ea1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514856"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="0b59f-102">Создание или изменение общедоступных федеративных поставщиков SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b59f-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b59f-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0b59f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0b59f-104">Подключение к общедоступным службам обмена мгновенными сообщениями позволяет пользователям организации использовать обмен мгновенными сообщениями для общения с пользователями служб обмена мгновенными сообщениями, предоставляемыми поставщиками служб обмена мгновенными сообщениями, включая Windows Live Messenger, Yahoo \! и AOL.</span><span class="sxs-lookup"><span data-stu-id="0b59f-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="0b59f-105">В Lync Server 2013 имеются общедоступные конфигурации поставщиков для America Online, Windows Live и Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="0b59f-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="0b59f-106">Обмен мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0b59f-106">instant messaging.</span></span> <span data-ttu-id="0b59f-107">Каждый общедоступный поставщик настраивается с полным доменным именем поставщика пограничного сервера, а уровень проверки по умолчанию **разрешает пользователям общаться только с людьми в своих списках контактов, которые используют этого поставщика**.</span><span class="sxs-lookup"><span data-stu-id="0b59f-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="0b59f-108">В качестве параметра по умолчанию ни один из открытых поставщиков не включен.</span><span class="sxs-lookup"><span data-stu-id="0b59f-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="0b59f-109">Перед включением общедоступных поставщиков следует полностью завершить лицензионное соглашение и подготовиться к работе.</span><span class="sxs-lookup"><span data-stu-id="0b59f-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="0b59f-110">Вы можете включить поставщика до завершения работы по лицензированию и подготовке.</span><span class="sxs-lookup"><span data-stu-id="0b59f-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="0b59f-111">Пользователи не смогут общаться с контактами для этих поставщиков, пока не будет выполнена предварительная работа.</span><span class="sxs-lookup"><span data-stu-id="0b59f-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="0b59f-112">Сведения о лицензировании и подготовке общедоступных поставщиков приведены в статье [Настройка политик для управления доступом пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="0b59f-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="0b59f-113">Используйте приведенную ниже процедуру для создания или изменения общедоступных поставщиков:</span><span class="sxs-lookup"><span data-stu-id="0b59f-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="0b59f-114">Чтобы создать или изменить общедоступного поставщика</span><span class="sxs-lookup"><span data-stu-id="0b59f-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="0b59f-115">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0b59f-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b59f-116">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b59f-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0b59f-117">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0b59f-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0b59f-118">На левой панели навигации щелкните **Федерация и внешний доступ**, затем щелкните **Федеративные поставщики SIP**.</span><span class="sxs-lookup"><span data-stu-id="0b59f-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="0b59f-119">Если необходимо создать нового общедоступного поставщика, щелкните **Создать**, затем **Общедоступный поставщик**.</span><span class="sxs-lookup"><span data-stu-id="0b59f-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="0b59f-120">Если необходимо изменить запись в списке общедоступных поставщиков, выберите общедоступного поставщика, щелкните **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0b59f-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="0b59f-121">На странице **Изменить федеративного поставщика SIP** можно указать или изменить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="0b59f-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="0b59f-122">**Включение связи с этим поставщиком**     При выборе этого параметра включается обмен мгновенными сообщениями с пользователями этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="0b59f-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="0b59f-123">**Имя поставщика:**     Обязательное свойство введите имя поставщика, которое будет отображаться в списке федеративных поставщиков SIP.</span><span class="sxs-lookup"><span data-stu-id="0b59f-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="0b59f-124">**Пограничная служба доступа (полное доменное имя):**     Обязательное свойство введите полное доменное имя службы пограничного доступа для настраиваемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="0b59f-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="0b59f-125">Эти сведения предоставляются в качестве элемента по умолчанию и должны изменяться только в том случае, если общедоступный поставщик вносит изменения в полное доменное имя службы пограничного доступа на общедоступном поставщике.</span><span class="sxs-lookup"><span data-stu-id="0b59f-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="0b59f-126">**Уровень проверки по умолчанию:**     Параметр по умолчанию, **позволяющий пользователям связываться с людьми в своих списках контактов, которые используют этого поставщика** , ограничивает общение с контактами, которые вы приняли и которые находятся в списке контактов.</span><span class="sxs-lookup"><span data-stu-id="0b59f-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="0b59f-p105">Выбор параметра **Разрешить пользователям взаимодействовать со всеми, кто работает с тем же поставщиком** снимает ограничения на общение с контактами того или иного поставщика. Любой пользователь из сети общедоступного поставщика может связываться с пользователями данной организации.</span><span class="sxs-lookup"><span data-stu-id="0b59f-p105">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="0b59f-129">Завершив настройку параметров, нажмите кнопку **Сохранить**, чтобы сохранить параметры, или **Отмена**, чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="0b59f-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b59f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0b59f-130">See Also</span></span>


[<span data-ttu-id="0b59f-131">Настройка политик для управления доступом открытых пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b59f-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="0b59f-132">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b59f-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

