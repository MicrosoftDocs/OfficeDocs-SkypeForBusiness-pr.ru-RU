---
title: Проверка развертывания edge в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Сводка. Узнайте, как проверить, работает ли развертывание сервера или пула серверов в Skype для бизнеса Server.
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804359"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="341f5-103">Проверка развертывания edge в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="341f5-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="341f5-104">**Сводка:** Узнайте, как проверить, работает ли развертывание сервера или пула в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="341f5-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="341f5-105">После развертывания пула edge server или edge server необходимо знать, правильно ли он работает.</span><span class="sxs-lookup"><span data-stu-id="341f5-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="341f5-106">Вот несколько факторов, которые помогут вам подтвердить, что ваша среда edge подключена к внутренним серверам, а также что внешние пользователи могут подключаться к среде Skype для бизнеса Server через ваш edge.</span><span class="sxs-lookup"><span data-stu-id="341f5-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="341f5-107">Проверка подключения между внутренними серверами и вашими edge-серверами</span><span class="sxs-lookup"><span data-stu-id="341f5-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="341f5-108">При автоматической проверке подключения в пуле edge server или edge Server при установке этих серверов вы можете подтвердить это самостоятельно с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="341f5-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="341f5-109">Запустите Get-CsManagementStoreReplicationStatus на внутреннем сервере, на котором имеется центральное хранилище управления, или на любом компьютере, который присоединился к домену, на котором установлены основные компоненты Skype для бизнеса Server (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="341f5-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="341f5-110">Начальный результат запуска этой команды может дать для репликации состояние False, а не True.</span><span class="sxs-lookup"><span data-stu-id="341f5-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="341f5-111">В этом случае запустите Invoke-CsManagementStoreReplication управления.</span><span class="sxs-lookup"><span data-stu-id="341f5-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="341f5-112">Дайте ему время для завершения репликации, а затем запустите Get-CsManagementStoreReplicationStatus снова.</span><span class="sxs-lookup"><span data-stu-id="341f5-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="341f5-113">Проверка возможности подключения для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="341f5-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="341f5-114">У нас есть отличный инструмент для подтверждения конфигурации вашего сервера и возможности подключения, отправки и получения правильных сообщений для сценариев с edge Server.</span><span class="sxs-lookup"><span data-stu-id="341f5-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="341f5-115">Это сайт [Remote Connectivity Anaylzer.](https://testconnectivity.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="341f5-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="341f5-116">Это сайт, который управляется и поддерживается службой поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="341f5-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="341f5-117">Чтобы использовать это средство, перейдите на веб-сайт и следуйте инструкциям, чтобы выбрать правильный сценарий.</span><span class="sxs-lookup"><span data-stu-id="341f5-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="341f5-118">Что следует учитывать при тестировании подключения внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="341f5-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="341f5-119">Любой тест доступа внешних пользователей должен включать каждый тип внутреннего пользователя, поддерживаемый организацией, который может включать любой из следующих типов или все следующие:</span><span class="sxs-lookup"><span data-stu-id="341f5-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="341f5-120">Пользователи по крайней мере из одного федератного домена (мы рекомендуем их все тестировать).</span><span class="sxs-lookup"><span data-stu-id="341f5-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="341f5-121">Анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="341f5-121">Anonymous users.</span></span>
    
- <span data-ttu-id="341f5-122">Пользователи в вашей организации, которые вошли в Skype для бизнеса удаленно, но не используют VPN.</span><span class="sxs-lookup"><span data-stu-id="341f5-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="341f5-123">Эти тесты определяют, является ли ваш edge Server:</span><span class="sxs-lookup"><span data-stu-id="341f5-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="341f5-124">Прослушивание необходимых портов с помощью клиента Telnet извне вашей сети.</span><span class="sxs-lookup"><span data-stu-id="341f5-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="341f5-125">Например: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="341f5-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="341f5-126">Предыдущий тест следует выполнить для портов, которые вы используете в пуле серверов или пуле, в зависимости от развертывания.</span><span class="sxs-lookup"><span data-stu-id="341f5-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="341f5-127">Выполнение точного разрешения внешнего DNS.</span><span class="sxs-lookup"><span data-stu-id="341f5-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="341f5-128">Из-за пределов сети выдайте ping каждое из внешних FQDNs вашего пула или пула.</span><span class="sxs-lookup"><span data-stu-id="341f5-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="341f5-129">Даже в случае сбой ping вы увидите IP-адреса, которые можно сравнить с ранее назначенной IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="341f5-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

