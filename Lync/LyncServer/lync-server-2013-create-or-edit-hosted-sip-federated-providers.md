---
title: 'Lync Server 2013: создание или изменение размещенных федеративных поставщиков SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937dfe2a63f755a7366fbb1b82c5593c466ac544
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="524c7-102">Создание или изменение размещенных федеративных поставщиков SIP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="524c7-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="524c7-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="524c7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="524c7-104">Служба подключения к обмену мгновенными сообщениями в организации позволяет пользователям организации обмениваться МГНОВЕНными сообщениями, чтобы общаться с пользователями служб обмена мгновенными сообщениями, предоставляемыми размещенными поставщиками, включая Microsoft Office 365 и Lync Online.</span><span class="sxs-lookup"><span data-stu-id="524c7-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="524c7-105">Каждый размещенный в узле поставщик настраивается с полным доменным именем пограничного сервера поставщика услуг и уровнем проверки по умолчанию **Разрешить пользователям взаимодействовать только с людьми в своих списках контактов, которые пользуются услугами данного поставщика**.</span><span class="sxs-lookup"><span data-stu-id="524c7-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="524c7-106">Следующая процедура используется для создания и изменения размещенных в узлах поставщиков:</span><span class="sxs-lookup"><span data-stu-id="524c7-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="524c7-107">Чтобы создать или изменить размещенных в узлах поставщиков</span><span class="sxs-lookup"><span data-stu-id="524c7-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="524c7-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="524c7-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="524c7-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="524c7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="524c7-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="524c7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="524c7-111">На левой панели навигации щелкните **Федерация и внешний доступ**, затем щелкните **Федеративные поставщики SIP**.</span><span class="sxs-lookup"><span data-stu-id="524c7-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="524c7-112">Если требуется создать нового размещенного в узле поставщика, щелкните **Создать**, а затем щелкните **Размещенный в узле поставщик**.</span><span class="sxs-lookup"><span data-stu-id="524c7-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="524c7-113">Если требуется изменить запись из списка размещенных в узлах поставщиков, выберите размещенного в узле поставщика, щелкните **Изменить**, затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="524c7-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="524c7-114">На странице **Изменить федеративного поставщика SIP** можно указать или изменить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="524c7-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="524c7-115">**Разрешить взаимодействие с этим поставщиком**   . при выборе этого параметра включается связь с пользователями этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="524c7-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="524c7-116">**Имя поставщика:**   обязательное свойство введите имя поставщика в том виде, в котором оно будет отображаться в списке федеративных поставщиков SIP.</span><span class="sxs-lookup"><span data-stu-id="524c7-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="524c7-117">**Пограничная служба доступа (полное доменное имя):**   обязательное свойство введите полное доменное имя службы пограничного доступа размещаемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="524c7-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="524c7-118">Эти сведения должны предоставляться размещенным в узле поставщиком и их допускается изменять только в том случае, если размещенный в узле поставщик изменяет полное доменное имя службы пограничного доступа на размещенном в узле поставщике.</span><span class="sxs-lookup"><span data-stu-id="524c7-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="524c7-119">**Уровень проверки по умолчанию:**   параметр по умолчанию, **позволяющий пользователям связываться с людьми в своих списках контактов, которые используют этого поставщика** , ограничивает общение с контактами, которые вы приняли и которые находятся в списке контактов.</span><span class="sxs-lookup"><span data-stu-id="524c7-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="524c7-p103">При выборе параметра **Разрешить связь со всеми, кто пользуется услугами данного поставщика** снимается ограничение, содержащее требование получения и принятия приглашения установить контакт. Этим параметром не ограничивается круг пользователей, которые могут связываться с вами из сети размещенного в узле поставщика.</span><span class="sxs-lookup"><span data-stu-id="524c7-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="524c7-122">Завершив настройку параметров, нажмите кнопку **Зафиксировать**, чтобы сохранить параметры, или **Отмена**, чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="524c7-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="524c7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="524c7-123">See Also</span></span>


[<span data-ttu-id="524c7-124">Настройка политик для управления доступом открытых пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="524c7-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="524c7-125">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="524c7-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

