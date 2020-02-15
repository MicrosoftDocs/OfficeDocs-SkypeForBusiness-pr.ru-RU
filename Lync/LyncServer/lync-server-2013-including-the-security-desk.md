---
title: 'Lync Server 2013: Включение службы безопасности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99f35087d03b046fade741140dc3f5522e6c6d05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="62293-102">Включая службу безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62293-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62293-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="62293-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="62293-p101">Вашей компании может потребоваться, чтобы в обработке экстренного звонка принимала участие служба безопасности. Чтобы облегчить принятие решения о способе интеграции службы безопасности с развертыванием E9-1-1, вам следует ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="62293-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="62293-106">**Вы хотите оповещать службу безопасности об экстренном звонке?**</span><span class="sxs-lookup"><span data-stu-id="62293-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="62293-107">Вы можете настроить политику расположения, чтобы Lync Server отправлял оповещения для обмена мгновенными сообщениями в SIP-адреса Lync для одного или нескольких сотрудников безопасности.</span><span class="sxs-lookup"><span data-stu-id="62293-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="62293-108">Эти предупреждения содержат имя, номер и расположение сотрудника, выполняющего экстренный звонок, и упрощают своевременное реагирование службы безопасности на экстренную ситуацию.</span><span class="sxs-lookup"><span data-stu-id="62293-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="62293-109">**Вы хотите подключать службу безопасности в каждому экстренному звонку в режиме конференции?**</span><span class="sxs-lookup"><span data-stu-id="62293-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="62293-p103">Если это поддерживается поставщиком услуг экстренных служб, вы можете настроить политику определения местоположения, чтобы включить в каждый экстренный звонок номер обратного вызова. Этот номер используется поставщиком, чтобы подключить службу безопасности вашей организации к экстренному вызову в режиме конференции. В политике определения местоположения эту конференцию можно настроить как одностороннюю (только прослушивание) или двухстороннюю (двунаправленная связь).</span><span class="sxs-lookup"><span data-stu-id="62293-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62293-p104">При необходимости вы можете настроить различных сотрудников экстренной службы для каждой политики определения местоположения. Это позволяет настроить ответ для разных областей вашей компании или создать отличную процедуру обработки экстренных звонков, поступающих не извне, изнутри сети. Можно использовать группы распределения для указания сотрудников, которых следует уведомлять.</span><span class="sxs-lookup"><span data-stu-id="62293-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

