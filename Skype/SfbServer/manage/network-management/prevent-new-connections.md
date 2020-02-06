---
title: Запрещение новых подключений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817458"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="be546-102">Предотвращение новых подключений к серверу Skype для бизнеса Server для обслуживания сервера</span><span class="sxs-lookup"><span data-stu-id="be546-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="be546-103">Skype для бизнеса Server позволяет перевести сервер в автономный режим (например, для применения обновлений программного обеспечения или оборудования) без потери обслуживания пользователей.</span><span class="sxs-lookup"><span data-stu-id="be546-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="be546-104">Если вы укажете параметр для предотвращения новых подключений и звонков на сервер в пуле, он перестанет выполнять новые подключения и вызовы, как только вы реализуете этот параметр.</span><span class="sxs-lookup"><span data-stu-id="be546-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="be546-105">Эти новые подключения и звонки перенаправляются через другие серверы в пуле.</span><span class="sxs-lookup"><span data-stu-id="be546-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="be546-106">Сервер, который препятствует новым подключениям, допускает продолжение сеансов в существующих соединениях, пока не завершится.</span><span class="sxs-lookup"><span data-stu-id="be546-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="be546-107">После того как все существующие сеансы будут завершены, сервер будет готов к переходу в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="be546-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="be546-108">Если вы не можете помешать новым подключениям к серверу переднего плана, то некоторые функции и службы в Skype для бизнеса Server полагаются на балансировку нагрузки DNS, чтобы убедиться, что она работает правильно.</span><span class="sxs-lookup"><span data-stu-id="be546-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="be546-109">Если вы не используете в пуле функцию балансировки нагрузки DNS, то при подключении через эти службы может не перенаправляться к другим серверам в течение периода, в течение которого сервер препятствует новым подключениям, и, следовательно, когда сервер переводится в автономный режим некоторые сеансы и звонки могут быть рвал.</span><span class="sxs-lookup"><span data-stu-id="be546-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="be546-110">Возможности, которые используют балансировку нагрузки DNS для обеспечения правильного функционирования этого параметра, описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="be546-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="be546-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="be546-111">Attendant</span></span>

  - <span data-ttu-id="be546-112">оповещений для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="be546-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="be546-113">"Группа ответа"</span><span class="sxs-lookup"><span data-stu-id="be546-113">Response Group application</span></span>

  - <span data-ttu-id="be546-114">"Объявление"</span><span class="sxs-lookup"><span data-stu-id="be546-114">Announcement application</span></span>

  - <span data-ttu-id="be546-115">приостановки вызовов</span><span class="sxs-lookup"><span data-stu-id="be546-115">Call Park application</span></span>

<span data-ttu-id="be546-116">Подробные сведения о балансировке нагрузки DNS можно найти в разделе [требования балансировки нагрузки для загрузки](../../plan-your-deployment/network-requirements/load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="be546-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="be546-117">В дополнение к предотвращению новых подключений для всех служб на сервере, на котором установлен Skype для бизнеса Server, вы также можете запретить новые подключения для отдельных служб Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="be546-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="be546-118">Например, этот метод полезен в ситуации, когда необходимо установить обновление для Skype для бизнеса Server, не требующее завершения работы всего сервера.</span><span class="sxs-lookup"><span data-stu-id="be546-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="be546-119">Обратите внимание, что при предотвращении подключений для одной службы необходимо выбрать службу, которая будет сгруппирована и отображена в списке служб Windows.</span><span class="sxs-lookup"><span data-stu-id="be546-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="be546-120">Например, клиентская служба Skype для бизнеса Server и агент сбора данных для наблюдения представляют собой отдельные службы Skype для бизнеса Server, но в списке служб Windows они консолидируются и отображаются как клиентский интерфейс Skype для бизнеса Server. сервиса.</span><span class="sxs-lookup"><span data-stu-id="be546-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="be546-121">Вы можете запретить новые соединения для серверной службы "клиент" в Skype для бизнеса Server, но вы не сможете помешать новым подключениям для этих двух отдельных служб Skype для бизнеса Server отдельно.</span><span class="sxs-lookup"><span data-stu-id="be546-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be546-122">Если вы настроили сервер для предотвращения новых подключений, а затем перезагрузите сервер, по умолчанию будет сразу же приступить к приему новых подключений после его запуска.</span><span class="sxs-lookup"><span data-stu-id="be546-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="be546-123">Чтобы не допустить этого, настройте сервер на приостановку и возобновление вручную, прежде чем перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="be546-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="be546-124">Запрещение новых подключений к Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="be546-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="be546-125">Войдите на локальный компьютер как член группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="be546-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="be546-126">Откройте консоль оснастки "службы": нажмите кнопку **Пуск**, наведите указатель на пункт **все программы**, выберите пункт **Администрирование**, а затем — пункт **службы**.</span><span class="sxs-lookup"><span data-stu-id="be546-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="be546-127">В списке дважды щелкните службу Windows, в которой вы хотите запретить новые подключения, в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="be546-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="be546-128">В диалоговом окне Свойства в разделе **состояние службы: запущено**выберите команду **приостановить**.</span><span class="sxs-lookup"><span data-stu-id="be546-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="be546-129">(Необязательно), но рекомендуется, рядом с полем **Тип запуска**выберите пункт **вручную**.</span><span class="sxs-lookup"><span data-stu-id="be546-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="be546-130">Если вы настроили сервер для предотвращения новых подключений, а затем перезагрузите сервер, по умолчанию будет сразу же приступить к приему новых подключений после его запуска.</span><span class="sxs-lookup"><span data-stu-id="be546-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="be546-131">Чтобы не допустить этого, настройте сервер на приостановку и возобновление вручную, прежде чем перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="be546-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
