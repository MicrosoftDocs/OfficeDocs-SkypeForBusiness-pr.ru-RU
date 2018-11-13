---
title: Устранение неполадок в диспетчер статистики для Скайп Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Сводка: Сведения для устранения неполадок развертывания из диспетчера статистики для Скайп Business Server.'
ms.openlocfilehash: 3a0bb2530e0b19685f28a747660e59b1fceec4e8
ms.sourcegitcommit: 8536a34cb13d40b30f84d95e6df10542ef85c36d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26292985"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="5ec61-103">Устранение неполадок в диспетчер статистики для Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="5ec61-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="5ec61-104">**Сводка:** Прочтите этот раздел для устранения неполадок развертывания из диспетчера статистики для Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="5ec61-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="5ec61-105">В этом разделе описывается развертывание диспетчера статистики Устранение неполадок, связанных с описанием событий, которые могут отображаться в журнале событий приложений и соответствующие действия, выполняемые для устранения события.</span><span class="sxs-lookup"><span data-stu-id="5ec61-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="5ec61-106">This topic contains the following sections:</span><span class="sxs-lookup"><span data-stu-id="5ec61-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="5ec61-107">События агента</span><span class="sxs-lookup"><span data-stu-id="5ec61-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="5ec61-108">События прослушивателя</span><span class="sxs-lookup"><span data-stu-id="5ec61-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="5ec61-109">Проблемы с веб-сайтом</span><span class="sxs-lookup"><span data-stu-id="5ec61-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="5ec61-110">События агента</span><span class="sxs-lookup"><span data-stu-id="5ec61-110">Agent events</span></span>
<span data-ttu-id="5ec61-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="5ec61-111"></span></span>

- <span data-ttu-id="5ec61-112">**1000** — не удается настроить ограничитель процессора (объект задания) — причина неизвестна</span><span class="sxs-lookup"><span data-stu-id="5ec61-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="5ec61-113">**1001** — ограничивать процесс не разрешено на процесс (возможно, помещенный в объект задания)</span><span class="sxs-lookup"><span data-stu-id="5ec61-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="5ec61-114">Агент выполняется внутри объекта задания Windows, чтобы автоматически ограничить занимаемый объем памяти.</span><span class="sxs-lookup"><span data-stu-id="5ec61-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="5ec61-115">Если агент не запускается, а эти записи о событиях присутствуют в журнале событий, объект задания не может быть создан на сервере.</span><span class="sxs-lookup"><span data-stu-id="5ec61-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="5ec61-116">Чтобы обойти эту проблему, может снять верхнее ограничение для памяти, изменив значение в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5ec61-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="5ec61-117">Поиск «MaxProcessMemoryMB» и измените значение «0», как показано:</span><span class="sxs-lookup"><span data-stu-id="5ec61-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="5ec61-118">При этом изменения, агент будут по-прежнему обычно используют \< 100 МБ памяти, однако он не будет принудительно более 300 МБ как используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ec61-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="5ec61-119">После внесения изменения рекомендуется тщательно следить за использованием памяти, чтобы агент не потреблял слишком большой объем памяти на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="5ec61-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="5ec61-120">**2000** — сбой инициализации клиента</span><span class="sxs-lookup"><span data-stu-id="5ec61-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="5ec61-121">**2001**— не удается установить подключение к службе на исходном IP-адресе</span><span class="sxs-lookup"><span data-stu-id="5ec61-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="5ec61-122">Если агенту не удается подключиться к компьютеру с прослушивателем, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="5ec61-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="5ec61-123">Убедитесь, что служба прослушивателя запущена на компьютере с прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="5ec61-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="5ec61-124">Если нет, убедитесь, что служба Redis работает на этом сервере, затем перезапустите службу прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="5ec61-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="5ec61-125">Проверьте журнал событий диспетчера статистики на компьютере прослушиватель, убедитесь, что отсутствуют проблемы с самой службы диспетчера статистики прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="5ec61-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="5ec61-126">С помощью средства проверки подключений, например, Telnet, проверьте подключение от компьютера с агентом к прослушивателю на нужном порте.</span><span class="sxs-lookup"><span data-stu-id="5ec61-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="5ec61-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span><span class="sxs-lookup"><span data-stu-id="5ec61-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="5ec61-128">Если прослушиватель компьютер не присоединен к домену, сети могут отображаться как public, и в этом случае не будет применяться правила брандмауэра, установленные с помощью диспетчера Статистика по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ec61-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="5ec61-129">**4000** — ошибка загрузки информации о сервере из прослушивателя (причина неизвестна)</span><span class="sxs-lookup"><span data-stu-id="5ec61-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="5ec61-130">**4001** — сервер не найден в топологии прослушивателя</span><span class="sxs-lookup"><span data-stu-id="5ec61-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="5ec61-131">Эта ошибка возникает, если сервер успешно подключается к прослушиватель, но сервер не был добавлен в топологию в кэше прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="5ec61-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="5ec61-132">Возможны следующие варианты решения:</span><span class="sxs-lookup"><span data-stu-id="5ec61-132">Resolution options:</span></span>
    
  - <span data-ttu-id="5ec61-p107">	Убедитесь, что вы выполнили инструкции по импорту топологии. См. статью [Импорт топологии](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="5ec61-p107">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="5ec61-135">Если агент находится на сервере, который не указан в топологии (например, узлы в кластере SQL AlwaysOn), необходимо добавить агент вручную, следуя инструкциям в статье [Импорт топологии](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="5ec61-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="5ec61-136">**4002** — недопустимый пароль прослушивателя</span><span class="sxs-lookup"><span data-stu-id="5ec61-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="5ec61-137">Зашифрованный пароль, который агент пытается использовать, не соответствует паролю для службы в самом прослушивателе.</span><span class="sxs-lookup"><span data-stu-id="5ec61-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="5ec61-138">Удалите агент и снова установите его, используя правильный пароль для службы.</span><span class="sxs-lookup"><span data-stu-id="5ec61-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="5ec61-139">**4003** — несоответствие Thumbprint сертификата</span><span class="sxs-lookup"><span data-stu-id="5ec61-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="5ec61-140">Thumbprint сертификата, назначенный агенту при установке, не соответствует Thumbprint в сертификате, который в настоящее время использует прослушиватель, поэтому в подключении будет отказано.</span><span class="sxs-lookup"><span data-stu-id="5ec61-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="5ec61-141">Удалите агент и снова установите его, используя правильный Thumbprint сертификата.</span><span class="sxs-lookup"><span data-stu-id="5ec61-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="5ec61-142">**4004** — недопустимый ответ или HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="5ec61-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="5ec61-143">Прослушиватель не отвечает ожидаемым состоянием.  </span><span class="sxs-lookup"><span data-stu-id="5ec61-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="5ec61-144">Если подключение осуществляется через прокси-сервер, проверьте конфигурацию прокси.</span><span class="sxs-lookup"><span data-stu-id="5ec61-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="5ec61-145">В журнале компьютера прослушиватель StatsMan проблемы с конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="5ec61-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="5ec61-146">**4005** — не удалось отменить последовательность XML</span><span class="sxs-lookup"><span data-stu-id="5ec61-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="5ec61-147">Информация о сервере на сервере прослушивателя повреждена или имеется несоответствие версий между компьютерами агента и прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="5ec61-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="5ec61-148">Убедитесь, что версии совпадают, и поищите проблемы в журнале событий прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="5ec61-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="5ec61-149">События прослушивателя</span><span class="sxs-lookup"><span data-stu-id="5ec61-149">Listener events</span></span>
<span data-ttu-id="5ec61-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="5ec61-150"></span></span>

- <span data-ttu-id="5ec61-151">**10000** — сбой запуска, причина неизвестна (не удается исправить, служба останавливается или завершает работу со сбоем)</span><span class="sxs-lookup"><span data-stu-id="5ec61-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="5ec61-152">**10001** — проблема конфигурации</span><span class="sxs-lookup"><span data-stu-id="5ec61-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="5ec61-153">Обычно эти ошибки возникают, когда файл [каталог_установки_прослушивателя]\PerfAgentListener.exe.config был изменен вручную, и приложению не удается его прочитать.</span><span class="sxs-lookup"><span data-stu-id="5ec61-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="5ec61-154">**10002** — ошибка инициализации HTTP-протокола прослушивателя</span><span class="sxs-lookup"><span data-stu-id="5ec61-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="5ec61-155">Это событие обычно записывается, если список управления доступом для URL-адресов неправильно настроен при установке или если сертификат SSL недействителен.</span><span class="sxs-lookup"><span data-stu-id="5ec61-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="5ec61-156">Убедитесь, что сертификат в конфигурации действителен.</span><span class="sxs-lookup"><span data-stu-id="5ec61-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="5ec61-157">Если это так, переустановите прослушиватель, следуя инструкциям в статье [Развертывание диспетчера статистики](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="5ec61-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="5ec61-158">**10003** — сбой Redis</span><span class="sxs-lookup"><span data-stu-id="5ec61-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="5ec61-159">**10004** — сбой инфраструктуры кэширования</span><span class="sxs-lookup"><span data-stu-id="5ec61-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="5ec61-160">**10007** — параметры (которые хранятся в Redis)</span><span class="sxs-lookup"><span data-stu-id="5ec61-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="5ec61-161">Прослушивателю не удалось связаться с Redis или извлечь сформированные данные из кэша и не удалось запуститься.</span><span class="sxs-lookup"><span data-stu-id="5ec61-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="5ec61-162">Убедитесь, что служба Redis запущена и правильно настроена на сервере.</span><span class="sxs-lookup"><span data-stu-id="5ec61-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="5ec61-163">**10005** — извлечение/синтаксический анализ информации о сервере</span><span class="sxs-lookup"><span data-stu-id="5ec61-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="5ec61-164">Информация о топологии в кэше Redis недействительна.</span><span class="sxs-lookup"><span data-stu-id="5ec61-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="5ec61-165">Сначала попробуйте перезапустить Redis и прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="5ec61-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="5ec61-166">Если ошибка останется, воссоздайте данные топологии, следуя инструкциям в статье [Импорт топологии](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="5ec61-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="5ec61-167">**10100** — сбой связи Redis</span><span class="sxs-lookup"><span data-stu-id="5ec61-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="5ec61-168">**10101** — продолжительный сбой связи Redis (каждые 60 секунд)</span><span class="sxs-lookup"><span data-stu-id="5ec61-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="5ec61-169">**30100** — устранение сбоя связи Redis</span><span class="sxs-lookup"><span data-stu-id="5ec61-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="5ec61-170">Эти события будут записаны, если прослушивателю не удается подключиться к Redis.</span><span class="sxs-lookup"><span data-stu-id="5ec61-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="5ec61-171">Убедитесь, что служба Redis запущена и подключение между службой и прослушивателем доступно.</span><span class="sxs-lookup"><span data-stu-id="5ec61-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="5ec61-172">**10200** — сбой записи Redis</span><span class="sxs-lookup"><span data-stu-id="5ec61-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="5ec61-173">**10201** — продолжительный сбой записи Redis (каждые 60 секунд)</span><span class="sxs-lookup"><span data-stu-id="5ec61-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="5ec61-174">**30100** — устранение сбоя записи Redis</span><span class="sxs-lookup"><span data-stu-id="5ec61-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="5ec61-175">Эти события будут записаны, если прослушивателю не удается выполнить запись в кэш Redis.</span><span class="sxs-lookup"><span data-stu-id="5ec61-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="5ec61-176">Убедитесь, что служба Redis запущена и подключение между службой и прослушивателем доступно.</span><span class="sxs-lookup"><span data-stu-id="5ec61-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="5ec61-177">**30000** — успешный запуск</span><span class="sxs-lookup"><span data-stu-id="5ec61-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="5ec61-178">Это событие записывается каждый раз при запуске прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="5ec61-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="5ec61-179">**22000** — инициализации из статистики агента Manager успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="5ec61-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="5ec61-180">**23000** — успешная инициализация EventLogQueryManager (первичная или после сбоя)</span><span class="sxs-lookup"><span data-stu-id="5ec61-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="5ec61-181">**24000** — успешная инициализация информации о сервере (первичная или после сбоя)</span><span class="sxs-lookup"><span data-stu-id="5ec61-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="5ec61-182">**25000** — прослушиватель снова в сети после ошибки публикации (или выполнена первая успешная публикация)</span><span class="sxs-lookup"><span data-stu-id="5ec61-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="5ec61-183">**5000** — автономный запуск прослушивателя для публикации данных</span><span class="sxs-lookup"><span data-stu-id="5ec61-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="5ec61-184">**5001** — прослушиватель работает в автономном режиме в течение длительного времени</span><span class="sxs-lookup"><span data-stu-id="5ec61-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="5ec61-185">Эти события полезны для мониторинга, оповещения и устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="5ec61-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="5ec61-186">Проблемы с веб-сайтом</span><span class="sxs-lookup"><span data-stu-id="5ec61-186">Website issues</span></span>
<span data-ttu-id="5ec61-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="5ec61-187"></span></span>

- <span data-ttu-id="5ec61-188">Входа повторяющихся предупреждений в Chrome - речь шла об ошибках, проблема устранена в версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="5ec61-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="5ec61-189">Убедитесь, что после обновления до последней версии диспетчера статистики Если вы видите запросы повторяющиеся для входа в браузере хрома.</span><span class="sxs-lookup"><span data-stu-id="5ec61-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="5ec61-190">To verify the version of the website you are running:</span><span class="sxs-lookup"><span data-stu-id="5ec61-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="5ec61-191">	В Проводнике файлов откройте (каталог по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5ec61-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="5ec61-192">Щелкните правой кнопкой мыши файл StatsManHubWebSite.dll и просмотрите его свойства.</span><span class="sxs-lookup"><span data-stu-id="5ec61-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="5ec61-193">Если компьютер не найден в представлении ландшафта KHI или в представлении сведений о счетчике, убедитесь, что он входит в состав сайта и пула.</span><span class="sxs-lookup"><span data-stu-id="5ec61-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="5ec61-194">Если нет, компьютер не будет отображаться в этих представлениях.</span><span class="sxs-lookup"><span data-stu-id="5ec61-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="5ec61-195">Дополнительные сведения об определении сайта и пула для сервера в топологии см. в статье [Импорт топологии](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="5ec61-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="5ec61-196">Версия продукта будет показана в сведениях описания.</span><span class="sxs-lookup"><span data-stu-id="5ec61-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="5ec61-197">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5ec61-197">For more information</span></span>
<span data-ttu-id="5ec61-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="5ec61-198"></span></span>

<span data-ttu-id="5ec61-199">Дополнительные сведения приведены далее.</span><span class="sxs-lookup"><span data-stu-id="5ec61-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="5ec61-200">Планирование для диспетчера статистики для Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="5ec61-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="5ec61-201">Развертывание диспетчера статистики для Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="5ec61-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="5ec61-202">Обновление статистики Manager для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5ec61-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- [<span data-ttu-id="5ec61-203">Блог, посвященный диспетчеру статистики Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5ec61-203">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/dodeitte/2015/10/24/skype-for-business-server-real-time-statistics-manager)
    

