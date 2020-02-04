---
title: 'Lync Server 2013: проверка соединений для внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1f8a9bbda54c596a9ccae8451b15ce7300bffd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="7bddc-102">Проверка соединений для внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bddc-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bddc-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7bddc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7bddc-104">Для проверки подключения внешних пользователей необходимо обеспечить соединение пользователей с сервером и портом службы Edge Access.</span><span class="sxs-lookup"><span data-stu-id="7bddc-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="7bddc-105">Ценный ресурс для подтверждения вашей конфигурации и возможности подключения, отправки и получения правильных сообщений о сценариях, для которых необходим внешний доступ, — это сайт анализатора удаленных подключений<http://www.testocsconnectivity.com>().</span><span class="sxs-lookup"><span data-stu-id="7bddc-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="7bddc-106">Управление сайтом и его обслуживание поддерживаются службой поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7bddc-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="7bddc-107">Чтобы подключиться к анализатору удаленных подключений, откройте веб-сайт в браузере и следуйте инструкциям по выбору сценария.</span><span class="sxs-lookup"><span data-stu-id="7bddc-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="7bddc-108">Проверка подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="7bddc-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="7bddc-109">Для проверки внешнего доступа пользователей следует включить все типы внешних пользователей, которые поддерживаются вашей организацией, в том числе любые из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="7bddc-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="7bddc-110">Пользователи по крайней мере одного федеративного домена и тестировать мгновенные сообщения, сведения о присутствии, а так же и на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="7bddc-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="7bddc-111">Пользователи всех общедоступных служб обмена мгновенными сообщениями, поддерживаемых вашей организацией (и для которых завершена подготовка).</span><span class="sxs-lookup"><span data-stu-id="7bddc-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="7bddc-112">Анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="7bddc-112">Anonymous users.</span></span>

  - <span data-ttu-id="7bddc-113">Пользователи в вашей организации, которые вошли в Lync удаленно, но не используют VPN.</span><span class="sxs-lookup"><span data-stu-id="7bddc-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="7bddc-114">Эти тесты определяют, является ли пограничный сервер:</span><span class="sxs-lookup"><span data-stu-id="7bddc-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="7bddc-115">Прослушивание необходимых портов с помощью клиента Telnet извне вашей сети.</span><span class="sxs-lookup"><span data-stu-id="7bddc-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="7bddc-116">Пример: Telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="7bddc-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="7bddc-117">Выполните описанные выше действия на портах, которые вы используете на пограничном сервере или в пуле пограничного сервера, в зависимости от вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="7bddc-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="7bddc-118">Выполнение точного разрешения внешнего DNS.</span><span class="sxs-lookup"><span data-stu-id="7bddc-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="7bddc-119">За пределами сети ping для каждого из внешних полных доменных имен в пуле EDGE или EDGE.</span><span class="sxs-lookup"><span data-stu-id="7bddc-119">From outside your network ping each of the external FQDN’s of your Edge or Edge pool.</span></span> <span data-ttu-id="7bddc-120">Даже если проверка связи не проходит, вы увидите IP-адреса, которые вы можете сравнить с назначенными вами адресами.</span><span class="sxs-lookup"><span data-stu-id="7bddc-120">Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

