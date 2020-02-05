---
title: Проверка пограничного развертывания в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Аннотация: Убедитесь, что развертывание пограничного сервера или пула пограничного сервера работает в Skype для бизнеса Server.'
ms.openlocfilehash: c73b77fd0171afe20f9e40b48c47ef4304df4c66
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768302"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="4ebdb-103">Проверка пограничного развертывания в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4ebdb-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="4ebdb-104">**Сводка:** Сведения о том, как убедиться, что развертывание пограничного сервера или пула пограничного сервера работает в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="4ebdb-105">После развертывания пограничного сервера или пула пограничного сервера вам нужно знать, что он работает правильно.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="4ebdb-106">Вот несколько вещей, которые помогут вам узнать, подключены ли к внутренним серверам подложки, а также в том, что ваши внешние пользователи могут подключаться к вашей среде Skype для бизнеса на вашем крае.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="4ebdb-107">Проверка подключения между внутренними и пограничными серверами</span><span class="sxs-lookup"><span data-stu-id="4ebdb-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="4ebdb-108">Несмотря на то, что проверка подключения выполняется автоматически на пограничном сервере или пуле пограничного сервера, когда пограничные серверы установлены, вы можете по-прежнему подтвердить это с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="4ebdb-109">Запустите командлет Get-Ксманажементсторерепликатионстатус на внутреннем сервере, на котором находится хранилище Центрального управления, или компьютер, подключенный к домену, на котором установлены основные компоненты Skype для бизнеса Server (Окскоре. msi).</span><span class="sxs-lookup"><span data-stu-id="4ebdb-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="4ebdb-p103">В начальных результатах запуска этой команды для репликации может быть указано состояние "False" вместо "True". В этом случае выполните командлет  Invoke-CsManagementStoreReplication. Дождитесь завершения репликации и выполните командлет Get-CsManagementStoreReplicationStatus еще раз.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="4ebdb-113">Проверка соединений для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4ebdb-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="4ebdb-114">У нас есть отличный инструмент для подтверждения конфигурации пограничного сервера, а также возможность подключения, отправки и получения правильных сообщений для сценариев пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="4ebdb-115">Это [сайт анайлзер с удаленным подключением](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="4ebdb-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="4ebdb-116">This is a site that's managed and maintained by Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="4ebdb-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="4ebdb-118">Вопросы, которые необходимо рассмотреть во время тестирования подключения внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4ebdb-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="4ebdb-119">Во все тесты для внешних пользователей должны включаться все типы внутренних пользователей, поддерживаемые в организации, включая любой из типов (или все типы) из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="4ebdb-120">Пользователи по крайней мере из одного федеративного домена (рекомендуется проверить все домены).</span><span class="sxs-lookup"><span data-stu-id="4ebdb-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="4ebdb-121">Анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-121">Anonymous users.</span></span>
    
- <span data-ttu-id="4ebdb-122">Пользователи в вашей организации, которые зарегистрированы в Skype для бизнеса в удаленном режиме, но не используют VPN.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="4ebdb-123">Эти тесты определяют, будет ли пограничный сервер:</span><span class="sxs-lookup"><span data-stu-id="4ebdb-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="4ebdb-124">Прослушивание необходимых портов с помощью клиента Telnet извне вашей сети.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="4ebdb-125">Пример: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="4ebdb-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="4ebdb-126">Вы должны выполнить предыдущий тест на используемых портах на пограничном сервере или в пуле пограничного сервера, в зависимости от того, какое развертывание вы используете.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="4ebdb-127">Выполнение точного разрешения внешнего DNS.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="4ebdb-128">За пределами вашей сети выполните команду ping для каждого из внешних полных доменных имен пограничного сервера или пула пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="4ebdb-129">Даже если проверка связи завершается сбоем, вы увидите IP-адреса, с помощью которых вы можете сравнить ранее назначенные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="4ebdb-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

