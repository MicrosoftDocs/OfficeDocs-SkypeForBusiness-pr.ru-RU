---
title: 'Lync Server 2013: Проверка подключения для внешних пользователей'
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
ms.openlocfilehash: a8d85b72572ba065f52e93ee34e6cb9324c2f647
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518646"
---
# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="8ea40-102">Проверка возможности подключения внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ea40-102">Verify connectivity for external users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ea40-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8ea40-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8ea40-104">Для проверки возможности подключения внешних пользователей необходимо обеспечить подключение пользователей к серверу и порт для пограничной службы доступа.</span><span class="sxs-lookup"><span data-stu-id="8ea40-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="8ea40-105">Ценный ресурс для подтверждения конфигурации и возможности подключения, отправки и получения правильных сообщений для сценариев, которые требуются для доступа внешних пользователей — это сайт анализатора удаленных подключений ( <http://www.testocsconnectivity.com> ).</span><span class="sxs-lookup"><span data-stu-id="8ea40-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="8ea40-106">Управление сайтом осуществляется службой поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8ea40-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="8ea40-107">Чтобы подключиться к анализатору удаленного подключения, откройте веб-сайт в браузере и следуйте инструкциям по выбору сценария.</span><span class="sxs-lookup"><span data-stu-id="8ea40-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="8ea40-108">Проверка возможности подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="8ea40-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="8ea40-109">Тесты  доступа внешних пользователей должны охватывать все типы внешних пользователей, которые поддерживаются в организации, частично или полностью включая приведенные далее.</span><span class="sxs-lookup"><span data-stu-id="8ea40-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="8ea40-110">Пользователи хотя бы из одного федеративного домена, для которых необходимо проверить обмен мгновенными сообщениями, функцию присутствия, аудио- и видеосвязь и общий доступ к рабочим столам.</span><span class="sxs-lookup"><span data-stu-id="8ea40-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="8ea40-111">Пользователи каждого общедоступного поставщика услуг обмена мгновенными сообщениями, поддерживаемого в организации (и для которого была выполнена подготовка).</span><span class="sxs-lookup"><span data-stu-id="8ea40-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="8ea40-112">Анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="8ea40-112">Anonymous users.</span></span>

  - <span data-ttu-id="8ea40-113">Пользователи в организации, входящие в Lync удаленно, но без использования VPN.</span><span class="sxs-lookup"><span data-stu-id="8ea40-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="8ea40-114">Эти тесты определяют, способен ли ваш пограничный сервер выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8ea40-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="8ea40-115">Прослушивание необходимых портов с помощью клиента Telnet извне вашей сети.</span><span class="sxs-lookup"><span data-stu-id="8ea40-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="8ea40-116">Пример: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="8ea40-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="8ea40-117">Выполнение предыдущего теста в портах, которые используются в пограничном сервере или в пограничном пуле, в зависимости от вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="8ea40-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="8ea40-118">Выполнение точного разрешения внешнего DNS.</span><span class="sxs-lookup"><span data-stu-id="8ea40-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="8ea40-p102">Извне сети проверьте связь для каждого из внешних полных доменных имен вашего пограничного сервера или пограничного пула. Даже если проверка связи выполнится неудачно, вы увидите IP-адреса, которые можно сравнить с назначенными вами.</span><span class="sxs-lookup"><span data-stu-id="8ea40-p102">From outside your network ping each of the external FQDN’s of your Edge or Edge pool. Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

