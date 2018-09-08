---
title: Проверка развертывания пограничного сервера в Скайп для Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Сводка: Узнайте, как проверить, развертывание пограничного сервера или пула пограничных серверов работает в Скайп для Business Server.'
ms.openlocfilehash: 267a02407a66614d0c78592da073307979136e39
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883550"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="6dbb8-103">Проверка развертывания пограничного сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="6dbb8-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="6dbb8-104">**Сводка:** Узнайте, как проверить, развертывание пограничного сервера или пула пограничных серверов работает в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="6dbb8-105">После развертывания пограничного сервера или пула пограничных серверов, необходимо знать, если он работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="6dbb8-106">Имеется несколько вещей, которые могут помочь с подтверждением подключен среды пограничного сервера для внутренних серверов и Кроме того, внешним пользователям подключения к Скайп для среды Business Server через вашей пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="6dbb8-107">Проверка подключения между внутренними и пограничными серверами</span><span class="sxs-lookup"><span data-stu-id="6dbb8-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="6dbb8-108">Во время проверки подключения выполняется автоматически в пограничного сервера или пула пограничных серверов при установке пограничного сервера, это может по-прежнему проверить ознакомиться с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="6dbb8-109">Используйте командлет Get-CsManagementStoreReplicationStatus на внутреннем сервере, имеющем хранилища централизованного управления или установлены любой компьютер домена соединенных на какие Скайп для Business Server компоненты ядра (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="6dbb8-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="6dbb8-p103">В начальных результатах запуска этой команды для репликации может быть указано состояние "False" вместо "True". В этом случае выполните командлет  Invoke-CsManagementStoreReplication. Дождитесь завершения репликации и выполните командлет Get-CsManagementStoreReplicationStatus еще раз.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="6dbb8-113">Проверка соединений для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="6dbb8-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="6dbb8-114">У нас есть отличное средство для проверки конфигурации пограничного сервера, а также возможность подключения, отправлять и получать правильные сообщения для сценариев пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="6dbb8-115">Это [удаленного подключения к Anaylzer сайта](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6dbb8-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="6dbb8-116">Это сайт, управляемых и поддерживается службой технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="6dbb8-117">Чтобы использовать это средство, перейдите на веб-сайт и следуйте инструкциям, чтобы при выборе подходящего сценария для вас.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="6dbb8-118">Вопросы, которые необходимо рассмотреть во время тестирования подключения внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="6dbb8-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="6dbb8-119">Во все тесты для внешних пользователей должны включаться все типы внутренних пользователей, поддерживаемые в организации, включая любой из типов (или все типы) из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="6dbb8-120">Пользователи по крайней мере из одного федеративного домена (рекомендуется проверить все домены).</span><span class="sxs-lookup"><span data-stu-id="6dbb8-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="6dbb8-121">Анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-121">Anonymous users.</span></span>
    
- <span data-ttu-id="6dbb8-122">Пользователи в вашей организации, входящие в Скайп для бизнеса удаленно, но не с помощью VPN.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="6dbb8-123">Эти тесты определяет необходимость пограничного сервера:</span><span class="sxs-lookup"><span data-stu-id="6dbb8-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="6dbb8-124">Прослушивание необходимых портов с помощью клиента Telnet извне вашей сети.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="6dbb8-125">Пример: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="6dbb8-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="6dbb8-126">Необходимо выполнение предыдущего теста в портах, которые вы используете на пограничном сервере или пула пограничных серверов, в зависимости от вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="6dbb8-127">Выполнение точного разрешения внешнего DNS.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="6dbb8-128">С за пределами сети, проверьте связь с каждой из внешние полные доменные имена пограничного сервера или пула пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="6dbb8-129">Даже в том случае, если команда ping завершается неудачно, вы увидите IP-адресов, которые можно сравнить IP-адресов, которые вы назначили ранее.</span><span class="sxs-lookup"><span data-stu-id="6dbb8-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

