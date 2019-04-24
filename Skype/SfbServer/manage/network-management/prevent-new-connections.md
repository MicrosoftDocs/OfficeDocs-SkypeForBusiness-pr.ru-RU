---
title: Запрет новых подключений
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: bc9b4a1e7d6e17f09643ff14ac0e69261c326922
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199022"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="c381e-102">Запрет новых подключений к Скайп для Business Server для обслуживания сервера</span><span class="sxs-lookup"><span data-stu-id="c381e-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="c381e-103">Скайп для Business Server позволяет отключать сервер (например, чтобы применить обновления программного обеспечения или оборудования) не прерывая обслуживание пользователей.</span><span class="sxs-lookup"><span data-stu-id="c381e-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="c381e-104">При указании вариант, чтобы запретить новые подключения или вызовов сервер в пуле, останавливает с удалением все новые подключения и вызовы по мере реализовать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="c381e-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="c381e-105">Эти новые подключения и вызовы направляются через другие серверы в пуле.</span><span class="sxs-lookup"><span data-stu-id="c381e-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="c381e-106">Сервер, который запрет новых подключений позволяет сеансов на существующие подключения продолжается, пока они естественным образом.</span><span class="sxs-lookup"><span data-stu-id="c381e-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="c381e-107">По окончании всех существующих сеансов сервер готов к доступны в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="c381e-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="c381e-108">При запретить новые подключения для сервера переднего плана, чтобы убедиться, что оно работает должным образом Балансировка нагрузки на DNS используют некоторые Скайп для компонентов Business Server и служб.</span><span class="sxs-lookup"><span data-stu-id="c381e-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="c381e-109">Если вы не используете в пуле Балансировка нагрузки на DNS, подключений через эти службы могут быть перенаправляться на других серверах в течение периода, что сервер не дает новых подключений и таким образом при сервера переводится в автономный режим может быть некоторые сеансы и вызовы прервана.</span><span class="sxs-lookup"><span data-stu-id="c381e-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="c381e-110">Функции, зависящие от для проверки правильности работы этот параметр, балансировка нагрузки на DNS, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c381e-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="c381e-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="c381e-111">Attendant</span></span>

  - <span data-ttu-id="c381e-112">оповещений для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="c381e-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="c381e-113">"Группа ответа"</span><span class="sxs-lookup"><span data-stu-id="c381e-113">Response Group application</span></span>

  - <span data-ttu-id="c381e-114">"Объявление"</span><span class="sxs-lookup"><span data-stu-id="c381e-114">Announcement application</span></span>

  - <span data-ttu-id="c381e-115">приостановки вызовов</span><span class="sxs-lookup"><span data-stu-id="c381e-115">Call Park application</span></span>

<span data-ttu-id="c381e-116">Сведения о Балансировка нагрузки на DNS содержатся [требования к балансировки нагрузки](../../plan-your-deployment/network-requirements/load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="c381e-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="c381e-117">В дополнение к запрет новых подключений для всех служб на сервере под управлением Скайп для Business Server, можно также запретить новые подключения для отдельных Скайп для служб Business Server.</span><span class="sxs-lookup"><span data-stu-id="c381e-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="c381e-118">Например этот метод полезен в ситуации, когда требуется применить Скайп для обновления Business Server, не требуется всего сервера, чтобы завершить работу.</span><span class="sxs-lookup"><span data-stu-id="c381e-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="c381e-119">Обратите внимание, что при запретить подключения для одной службы, необходимо выбрать службу как сгруппированные и отображается в списке служб Windows.</span><span class="sxs-lookup"><span data-stu-id="c381e-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="c381e-120">Например агент коллекции данных для отслеживания и Скайп для службы интерфейсного сервера Business отдельные Скайп для служб Business Server, но в списке служб Windows они являются консолидированный и отображаться в виде Скайп Business сервера переднего плана Служба.</span><span class="sxs-lookup"><span data-stu-id="c381e-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="c381e-121">Можно запретить новые подключения для Скайп для службы Business сервера переднего плана, но вы не можете запретить новые подключения для этих двух отдельных базового Скайп для служб Business Server отдельно.</span><span class="sxs-lookup"><span data-stu-id="c381e-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c381e-122">При установке с сервером, чтобы запретить новые подключения, а затем перезапустите сервер по умолчанию на сервере сразу же начнется принимать новые подключения после его запуска.</span><span class="sxs-lookup"><span data-stu-id="c381e-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="c381e-123">Чтобы предотвратить это, задайте на сервере только Приостановка и возобновление вручную, перед перезапуском сервера.</span><span class="sxs-lookup"><span data-stu-id="c381e-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="c381e-124">Чтобы запретить новые подключения к Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c381e-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="c381e-125">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="c381e-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="c381e-126">Откройте консоль службы оснастку: нажмите кнопку **Пуск**, последовательно выберите **Все программы**, **Администрирование**и затем щелкните **службы**.</span><span class="sxs-lookup"><span data-stu-id="c381e-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="c381e-127">В списке дважды щелкните Скайп для службы Business Server Windows, к которому вы хотите запретить новые подключения.</span><span class="sxs-lookup"><span data-stu-id="c381e-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="c381e-128">В диалоговом окне Свойства в разделе **состояние службы: запущена**, нажмите кнопку **Приостановить**.</span><span class="sxs-lookup"><span data-stu-id="c381e-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="c381e-129">При необходимости но рекомендуется, рядом с полем **Тип запуска**выберите **вручную**.</span><span class="sxs-lookup"><span data-stu-id="c381e-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c381e-130">При установке с сервером, чтобы запретить новые подключения, а затем перезапустите сервер по умолчанию на сервере сразу же начнется принимать новые подключения после его запуска.</span><span class="sxs-lookup"><span data-stu-id="c381e-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="c381e-131">Чтобы предотвратить это, задайте на сервере только Приостановка и возобновление вручную, перед перезапуском сервера.</span><span class="sxs-lookup"><span data-stu-id="c381e-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
