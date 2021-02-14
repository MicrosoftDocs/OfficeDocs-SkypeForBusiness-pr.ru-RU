---
title: Устранение проблем диспетчера статистики в Skype для бизнеса Server
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
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: Сводка. Ознакомьтесь с этой темой, чтобы устранить неполадки при развертывании диспетчера статистики в Skype для бизнеса Server.
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821779"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="6cabd-103">Устранение проблем диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6cabd-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="6cabd-104">**Сводка:** Прочитайте этот раздел, чтобы устранить неполадки развертывания диспетчера статистики в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6cabd-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="6cabd-105">В этом разделе описывается, как устранить неполадки в развертывании диспетчера статистики, описывая события, которые можно увидеть в журнале событий приложений, а также соответствующие действия, которые можно принять для устранения этого события.</span><span class="sxs-lookup"><span data-stu-id="6cabd-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="6cabd-106">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="6cabd-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="6cabd-107">События агента</span><span class="sxs-lookup"><span data-stu-id="6cabd-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="6cabd-108">События прослушиватель</span><span class="sxs-lookup"><span data-stu-id="6cabd-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="6cabd-109">Проблемы с веб-сайтом</span><span class="sxs-lookup"><span data-stu-id="6cabd-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="6cabd-110">События агента</span><span class="sxs-lookup"><span data-stu-id="6cabd-110">Agent events</span></span>
<span data-ttu-id="6cabd-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="6cabd-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="6cabd-112">**1000** — не удается настроить обработчик (объект задания) — неизвестная причина</span><span class="sxs-lookup"><span data-stu-id="6cabd-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="6cabd-113">**1001** — ограничение процесса не разрешено для процесса (возможно, уже внутри объекта задания)</span><span class="sxs-lookup"><span data-stu-id="6cabd-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="6cabd-114">Агент выполняется внутри объекта задания Windows, чтобы автоматически ограничить объем памяти.</span><span class="sxs-lookup"><span data-stu-id="6cabd-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="6cabd-115">Если агент не запустится и эти записи событий присутствуют в журнале событий, объект задания не может быть сгенелен на сервере.</span><span class="sxs-lookup"><span data-stu-id="6cabd-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="6cabd-116">Чтобы обойти эту возможность, верхний предел памяти можно удалить, изменив значение в файле config:</span><span class="sxs-lookup"><span data-stu-id="6cabd-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="6cabd-117">Найди "MaxProcessMemoryMB" и измените значение на "0", как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="6cabd-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="6cabd-118">Если это изменение внося, агент по-прежнему будет потреблять 100 МБ памяти, но не будет принудительно ограничен \< до 300 МБ, как по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6cabd-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="6cabd-119">При изменении рекомендуется внимательно следить за использованием памяти, чтобы агент не потреблял большой объем памяти на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="6cabd-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="6cabd-120">**2000** — сбой инициализации клиента</span><span class="sxs-lookup"><span data-stu-id="6cabd-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="6cabd-121">**2001**— подключение к службе на любом из исходных IP-адресов не может быть выполнено</span><span class="sxs-lookup"><span data-stu-id="6cabd-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="6cabd-122">Если агенту не удается подключиться к компьютеру прослушиватель, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="6cabd-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="6cabd-123">Убедитесь, что служба прослушиватель запущена на компьютере прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6cabd-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="6cabd-124">В этом случае убедитесь, что Redis запущен на этом сервере, а затем перезапустите службу прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6cabd-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="6cabd-125">Проверьте журнал событий диспетчера статистики на компьютере прослушиватель, чтобы убедиться, что нет проблем с самой службой прослушиватель диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="6cabd-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="6cabd-126">Используйте средство подключения, например telnet, для проверки подключения компьютера агента к прослушивательу на правильном порте.</span><span class="sxs-lookup"><span data-stu-id="6cabd-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="6cabd-127">Если нет, убедитесь, что на компьютере прослушиватель включено правило входящих брандмауэров для сетевого типа, к который подключен компьютер прослушиватель (частный,общедоступный/домен).</span><span class="sxs-lookup"><span data-stu-id="6cabd-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="6cabd-128">Если компьютер прослушиватель не присоединяется к домену, сеть может быть указана как общедоступный, и в этом случае правила брандмауэра, установленные с помощью диспетчера статистики, не будут применяться по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6cabd-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="6cabd-129">**4000** — сбой загрузки данных сервера из прослушиватель (неизвестная причина)</span><span class="sxs-lookup"><span data-stu-id="6cabd-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="6cabd-130">**4001** — сервер не найден в топологии прослушиватель</span><span class="sxs-lookup"><span data-stu-id="6cabd-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="6cabd-131">Эта ошибка возникает, если сервер успешно подключается к прослушивательу, но сервер не был добавлен в топологию в кэше прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6cabd-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="6cabd-132">Варианты разрешения:</span><span class="sxs-lookup"><span data-stu-id="6cabd-132">Resolution options:</span></span>
    
  - <span data-ttu-id="6cabd-133">Убедитесь, что вы следовали инструкциям по импорту топологии.</span><span class="sxs-lookup"><span data-stu-id="6cabd-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="6cabd-134">См. ["Импорт топологии".](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="6cabd-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="6cabd-135">Если агент находится на сервере, который не указан в топологии (например, узлы в кластере SQL AlwaysOn), вам потребуется добавить [](deploy.md#BKMK_ImportTopology)агент вручную, следуя инструкциям в импорте топологии.</span><span class="sxs-lookup"><span data-stu-id="6cabd-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="6cabd-136">**4002** — недопустимый пароль прослушиватель</span><span class="sxs-lookup"><span data-stu-id="6cabd-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="6cabd-137">Зашифрованный пароль, который пытается использовать агент, не совпадает с паролем службы в самом прослушивателье.</span><span class="sxs-lookup"><span data-stu-id="6cabd-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="6cabd-138">Удалить агент и повторно установить его с использованием правильного пароля службы.</span><span class="sxs-lookup"><span data-stu-id="6cabd-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="6cabd-139">**4003** — несоответствие отпечатков сертификатов</span><span class="sxs-lookup"><span data-stu-id="6cabd-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="6cabd-140">Отпечаток сертификата, заданный агенту во время установки, не совпадает с отпечатком сертификата, используемом прослушивачиком, поэтому от подключения будет отказано.</span><span class="sxs-lookup"><span data-stu-id="6cabd-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="6cabd-141">Удалить агент и повторно установить его с использованием правильного отпечатка сертификата.</span><span class="sxs-lookup"><span data-stu-id="6cabd-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="6cabd-142">**4004** — недопустимый ответ или HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="6cabd-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="6cabd-143">Прослушиватель не отвечает ожидаемым состоянием.</span><span class="sxs-lookup"><span data-stu-id="6cabd-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="6cabd-144">Если подключение подключено к прокси-серверу, проверьте конфигурацию прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="6cabd-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="6cabd-145">Проверьте журнал StatsMan компьютера прослушиватель на проблемы с его конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="6cabd-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="6cabd-146">**4005** — не удалось десериализировать XML</span><span class="sxs-lookup"><span data-stu-id="6cabd-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="6cabd-147">Сведения о сервере на сервере прослушиватель повреждены или могут быть несоответствия версий между агентом и компьютерами прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6cabd-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="6cabd-148">Убедитесь, что версии совпадают, и проверьте журнал событий прослушиватель на проблемы.</span><span class="sxs-lookup"><span data-stu-id="6cabd-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="6cabd-149">События прослушиватель</span><span class="sxs-lookup"><span data-stu-id="6cabd-149">Listener events</span></span>
<span data-ttu-id="6cabd-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="6cabd-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="6cabd-151">**10000** — неизвестная причина сбоя при запуске (они невозмежны, и служба остановится или сбой в результате)</span><span class="sxs-lookup"><span data-stu-id="6cabd-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="6cabd-152">**10001** — проблема конфигурации</span><span class="sxs-lookup"><span data-stu-id="6cabd-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="6cabd-153">Обычно это происходит, когда файл [listener_install_location]\PerfAgentListener.exe.config изменен вручную и не может быть прочитан приложением.</span><span class="sxs-lookup"><span data-stu-id="6cabd-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="6cabd-154">**10002** — ошибка инициализации HTTP-прослушиватель</span><span class="sxs-lookup"><span data-stu-id="6cabd-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="6cabd-155">Как правило, это событие регистрируется, если ACL URL-адреса неправильно заданной во время установки или если сертификат SSL недействителен.</span><span class="sxs-lookup"><span data-stu-id="6cabd-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="6cabd-156">Убедитесь, что сертификат в конфигурации действителен.</span><span class="sxs-lookup"><span data-stu-id="6cabd-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="6cabd-157">В этом случае переустановите прослушиватель в соответствии с инструкциями в [диспетчере статистики.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="6cabd-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="6cabd-158">**10003** — сбой Redis</span><span class="sxs-lookup"><span data-stu-id="6cabd-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="6cabd-159">**10004** — сбой инфраструктуры кэшинга</span><span class="sxs-lookup"><span data-stu-id="6cabd-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="6cabd-160">**10007** — параметры (сохраненные в redis)</span><span class="sxs-lookup"><span data-stu-id="6cabd-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="6cabd-161">Прослушиватель не смог связаться с Redis или получить сформированные данные из кэша и не мог запуститься.</span><span class="sxs-lookup"><span data-stu-id="6cabd-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="6cabd-162">Убедитесь, что служба Redis запущена и настроена правильно на сервере.</span><span class="sxs-lookup"><span data-stu-id="6cabd-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="6cabd-163">**10005** — итеряль и разбиение информации о сервере</span><span class="sxs-lookup"><span data-stu-id="6cabd-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="6cabd-164">Недопустимые сведения о топологии в кэше Redis.</span><span class="sxs-lookup"><span data-stu-id="6cabd-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="6cabd-165">Сначала перезапустите Redis и прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6cabd-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="6cabd-166">Если ошибка сохраняется, см. ["Импорт топологии для](deploy.md#BKMK_ImportTopology) воссоздания данных топологии".</span><span class="sxs-lookup"><span data-stu-id="6cabd-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="6cabd-167">**10100** — отключение Redis PING</span><span class="sxs-lookup"><span data-stu-id="6cabd-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="6cabd-168">**10101** — постоянное отключение Redis PING (каждые 60 секунд)</span><span class="sxs-lookup"><span data-stu-id="6cabd-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="6cabd-169">**30100** — восстановлено отключение PING Redis</span><span class="sxs-lookup"><span data-stu-id="6cabd-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="6cabd-170">Они будут регистрироваться, если прослушиватель не может подключиться к Redis.</span><span class="sxs-lookup"><span data-stu-id="6cabd-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="6cabd-171">Убедитесь, что redis запущен, и доступно сетевое подключение между прослушивательом и Redis.</span><span class="sxs-lookup"><span data-stu-id="6cabd-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="6cabd-172">**10200** — с отключение записи Redis</span><span class="sxs-lookup"><span data-stu-id="6cabd-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="6cabd-173">**10201** — продолжающееся отключение записи Redis (каждые 60 секунд)</span><span class="sxs-lookup"><span data-stu-id="6cabd-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="6cabd-174">**30100** — устранено отключение записи Redis</span><span class="sxs-lookup"><span data-stu-id="6cabd-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="6cabd-175">Они будут записываться в журнал, если прослушиватель не сможет записать данные в кэш Redis.</span><span class="sxs-lookup"><span data-stu-id="6cabd-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="6cabd-176">Убедитесь, что redis запущен, и доступно сетевое подключение между прослушивательом и Redis.</span><span class="sxs-lookup"><span data-stu-id="6cabd-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="6cabd-177">**30000** — успешно запущено</span><span class="sxs-lookup"><span data-stu-id="6cabd-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="6cabd-178">Регистрируется каждый раз, когда прослушиватель запущен.</span><span class="sxs-lookup"><span data-stu-id="6cabd-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="6cabd-179">**22000** — успешно инициализация агента диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="6cabd-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="6cabd-180">**23000** — инициализация EventLogQueryManager успешно (в первый раз или после сбоя)</span><span class="sxs-lookup"><span data-stu-id="6cabd-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="6cabd-181">**24000** — инициализация serverinfo успешно (в первый раз или после сбоя)</span><span class="sxs-lookup"><span data-stu-id="6cabd-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="6cabd-182">**25000** — прослушиватель снова в сети после сбоя публикации (или первой успешной публикации)</span><span class="sxs-lookup"><span data-stu-id="6cabd-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="6cabd-183">**5000** — запуск прослушиватель в автономном режиме для публикации данных</span><span class="sxs-lookup"><span data-stu-id="6cabd-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="6cabd-184">**5001** — прослушиватель остается в автономном режиме в течение длительного периода времени</span><span class="sxs-lookup"><span data-stu-id="6cabd-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="6cabd-185">Эти события могут быть полезны при отслеживании, оповещении и очистке проблем.</span><span class="sxs-lookup"><span data-stu-id="6cabd-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="6cabd-186">Проблемы с веб-сайтом</span><span class="sxs-lookup"><span data-stu-id="6cabd-186">Website issues</span></span>
<span data-ttu-id="6cabd-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="6cabd-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="6cabd-188">Повторяющиеся запросы входа в Chrome — это ошибка, которая была устранена в версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="6cabd-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="6cabd-189">Убедитесь, что вы обновили до последней версии диспетчера статистики, если в браузере Chrome вы видите повторяемую подсказку для входа.</span><span class="sxs-lookup"><span data-stu-id="6cabd-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="6cabd-190">Чтобы проверить версию веб-сайта, вы работаете:</span><span class="sxs-lookup"><span data-stu-id="6cabd-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="6cabd-191">В проводнике откройте (каталог по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6cabd-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="6cabd-192">Щелкните правой кнопкой мыши StatsManHubWebSite.dll и просмотрете его свойства.</span><span class="sxs-lookup"><span data-stu-id="6cabd-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="6cabd-193">Если компьютер не может быть найден в представлении "Альбомная" или "Сведения счетчика", убедитесь, что он является членом сайта и пула.</span><span class="sxs-lookup"><span data-stu-id="6cabd-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="6cabd-194">Если это не так, он не будет отображаться в этих представлениях.</span><span class="sxs-lookup"><span data-stu-id="6cabd-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="6cabd-195">Сведения об определении сайта и пула для сервера в топологии см. в под вопросе "Импорт [топологии".](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="6cabd-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="6cabd-196">Версия продукта будет показана в описании.</span><span class="sxs-lookup"><span data-stu-id="6cabd-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="6cabd-197">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6cabd-197">For more information</span></span>
<span data-ttu-id="6cabd-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="6cabd-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="6cabd-199">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="6cabd-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="6cabd-200">Планирование диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6cabd-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="6cabd-201">Развертывание диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6cabd-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="6cabd-202">Обновление диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6cabd-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
