---
title: Предотвращение новых подключений
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823469"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="5ddec-102">Предотвращение новых подключений к Skype для бизнеса Server для обслуживания сервера</span><span class="sxs-lookup"><span data-stu-id="5ddec-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="5ddec-103">Skype для бизнеса Server позволяет отодействовать сервер (например, для применения обновлений программного обеспечения или оборудования) без потери службы для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5ddec-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="5ddec-p101">Как только вы выбираете параметр, блокирующий новые подключения или вызовы к серверу в пуле, сервер перестает принимать новые подключения и вызовы. Эти новые подключения и вызовы маршрутизируются через другие серверы в пуле. На сервере, блокирующем новые подключения, существующие сеансы могут продолжать выполняться. Когда все существующие сеансы будут завершены, сервер можно отключить.</span><span class="sxs-lookup"><span data-stu-id="5ddec-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="5ddec-108">При предотвращении новых подключений к серверу переднего сервера некоторые функции и службы Skype для бизнеса Server используют балансировку нагрузки на DNS, чтобы обеспечить правильную работу.</span><span class="sxs-lookup"><span data-stu-id="5ddec-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="5ddec-109">Если вы не используете балансировку нагрузки на DNS в пуле, подключения через эти службы могут не перена маршрутироваться на другие серверы в течение периода, когда сервер препятствует новым подключениям, и таким образом, когда сервер перезагружен в автономном режиме, некоторые сеансы и вызовы могут быть прерваны.</span><span class="sxs-lookup"><span data-stu-id="5ddec-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="5ddec-110">Функции, которые используют балансировку нагрузки на DNS для обеспечения правильной работы этого параметра, следуют следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5ddec-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="5ddec-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="5ddec-111">Attendant</span></span>

  - <span data-ttu-id="5ddec-112">приложение "Объявления для конференц-связи";</span><span class="sxs-lookup"><span data-stu-id="5ddec-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="5ddec-113">приложение группы ответа;</span><span class="sxs-lookup"><span data-stu-id="5ddec-113">Response Group application</span></span>

  - <span data-ttu-id="5ddec-114">Приложение " Оповещение"</span><span class="sxs-lookup"><span data-stu-id="5ddec-114">Announcement application</span></span>

  - <span data-ttu-id="5ddec-115">Приложение "Парковка вызовов"</span><span class="sxs-lookup"><span data-stu-id="5ddec-115">Call Park application</span></span>

<span data-ttu-id="5ddec-116">Подробные сведения о балансировку нагрузки на DNS см. в сведениях о [требованиях балансировки нагрузки.](../../plan-your-deployment/network-requirements/load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="5ddec-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="5ddec-117">Помимо предотвращения новых подключений для всех служб на сервере skype для бизнеса Server, можно также запретить новые подключения для отдельных служб Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5ddec-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="5ddec-118">Например, этот метод полезен в ситуации, когда необходимо применить обновление Skype для бизнеса Server, которое не требует отключения всего сервера.</span><span class="sxs-lookup"><span data-stu-id="5ddec-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="5ddec-119">Обратите внимание на то, что при блокировании подключений для службы ее необходимо выбирать с учетом того, как она сгруппирована и отображается в списке служб Windows.</span><span class="sxs-lookup"><span data-stu-id="5ddec-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="5ddec-120">Например, служба Front-End Skype для бизнеса Server и агент сбора данных для мониторинга — это отдельные службы Skype для бизнеса Server, но в списке служб Windows они консолидированы и показаны в качестве службы переднего сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5ddec-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="5ddec-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span><span class="sxs-lookup"><span data-stu-id="5ddec-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ddec-p104">Если вы запретили новые подключения к серверу и затем перезагрузили его, после запуска по умолчанию сервер начнет принимать новые подключения. Во избежание этого перед перезапуском сервера настройте на нем приостановку и возобновление работы только в ручном режиме.</span><span class="sxs-lookup"><span data-stu-id="5ddec-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="5ddec-124">Предотвращение новых подключений к Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5ddec-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="5ddec-125">Войдите на локальный компьютер в качестве члена группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="5ddec-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="5ddec-126">Откройте консоль оснастки "Службы": нажмите кнопку "Начните", выберите пункты "Все программы", "Администрирование" и **"Службы".**  </span><span class="sxs-lookup"><span data-stu-id="5ddec-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="5ddec-127">В списке дважды щелкните службу Windows Skype для бизнеса Server, к которой необходимо запретить новые подключения.</span><span class="sxs-lookup"><span data-stu-id="5ddec-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="5ddec-128">В диалоговом окне "Свойства" в поле **Состояние службы: запущена** щелкните **Приостановить**.</span><span class="sxs-lookup"><span data-stu-id="5ddec-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="5ddec-129">В столбце **Тип запуска** рекомендуется (но не обязательно) выбрать пункт **Вручную**.</span><span class="sxs-lookup"><span data-stu-id="5ddec-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5ddec-p105">Если вы запретили новые подключения к серверу и затем перезагрузили его, после запуска по умолчанию сервер начнет принимать новые подключения. Во избежание этого перед перезапуском сервера настройте на нем приостановку и возобновление работы только в ручном режиме.</span><span class="sxs-lookup"><span data-stu-id="5ddec-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
