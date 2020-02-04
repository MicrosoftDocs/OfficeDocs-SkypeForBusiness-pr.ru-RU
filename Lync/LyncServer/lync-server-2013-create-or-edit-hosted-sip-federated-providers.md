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
ms.openlocfilehash: d6c97255ce1dc9fce00d9eca6f358f4c68e1ff8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="2811a-102">Создание или изменение размещенных федеративных поставщиков SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2811a-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2811a-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2811a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2811a-104">Подключение к службе обмена мгновенными сообщениями (IM) позволяет пользователям в вашей организации общаться с пользователями служб обмена мгновенными сообщениями, предоставляемыми поставщиками услуг, в том числе с помощью Microsoft Office 365 и Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2811a-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="2811a-105">Для каждого поставщика услуг размещения задано полное доменное имя поставщика, а уровень проверки по умолчанию **позволяет пользователям общаться только с людьми из списка контактов, который использует этот поставщик**.</span><span class="sxs-lookup"><span data-stu-id="2811a-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="2811a-106">Для создания и изменения внутрипроцессных поставщиков выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2811a-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="2811a-107">Создание и изменение размещенных поставщиков</span><span class="sxs-lookup"><span data-stu-id="2811a-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="2811a-108">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2811a-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2811a-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2811a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2811a-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2811a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2811a-111">На панели навигации слева выберите пункт **интеграция и внешний доступ**, а затем — **Федеративные поставщики SIP**.</span><span class="sxs-lookup"><span data-stu-id="2811a-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="2811a-112">Если вам нужно создать нового поставщика услуг размещения, нажмите кнопку **создать** , а затем выберите пункт **внутрипроцессный поставщик**.</span><span class="sxs-lookup"><span data-stu-id="2811a-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="2811a-113">Если вам нужно изменить запись из списка размещенных поставщиков, выберите поставщика услуг, нажмите кнопку **изменить**, а затем выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="2811a-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="2811a-114">На странице " **Изменение поставщика SIP-Федерации** " можно ввести или изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2811a-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="2811a-115">**Включите связь с этим поставщиком**   , выбрав этот параметр, чтобы включить связь с пользователями этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="2811a-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="2811a-116">**Имя поставщика:**   обязательное свойство введите имя поставщика, так как оно будет отображаться в списке поставщиков услуг-Федерации SIP.</span><span class="sxs-lookup"><span data-stu-id="2811a-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="2811a-117">**Служба пограничного доступа (полное доменное имя):**   обязательное свойство введите полное доменное имя службы Edge для доступного поставщика услуг размещения, который вы настраиваете.</span><span class="sxs-lookup"><span data-stu-id="2811a-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="2811a-118">Эти данные должны предоставляться поставщиком услуг размещения и должны изменяться только в том случае, если поставщик услуг хостинга вносит изменения в полное доменное имя службы EDGE на доступ на размещенном поставщике.</span><span class="sxs-lookup"><span data-stu-id="2811a-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="2811a-119">**Уровень проверки по умолчанию:**   Настройка по умолчанию, **разрешающая пользователям общаться с людьми из списка контактов, которые используют этот поставщик** , ограничивает общение с контактами, которые вы приняли, и находятся в вашем списке контактов.</span><span class="sxs-lookup"><span data-stu-id="2811a-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="2811a-120">Выбрав **параметр Разрешить пользователям общаться с кем угодно с помощью этого поставщика** , вы удаляете ограничение, которое вы должны получить и принять приглашение на контакт.</span><span class="sxs-lookup"><span data-stu-id="2811a-120">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="2811a-121">Этот параметр не ограничивает список пользователей, которые могут общаться с вами из сети размещенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="2811a-121">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="2811a-122">Завершив настройку параметров **, нажмите кнопку Сохранить для** сохранения или кнопку **Отмена** , чтобы отменить изменения.</span><span class="sxs-lookup"><span data-stu-id="2811a-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2811a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2811a-123">See Also</span></span>


[<span data-ttu-id="2811a-124">Конфигурация политик для управления общим доступом пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2811a-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="2811a-125">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2811a-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

