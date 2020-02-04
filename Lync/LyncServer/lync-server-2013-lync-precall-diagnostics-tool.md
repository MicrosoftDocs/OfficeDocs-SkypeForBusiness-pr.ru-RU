---
title: 'Lync Server 2013: средство диагностики предзвонков для Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 004d3b30dc2c2886eb7a2d8977f1da062277cc92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="44896-102">Средство диагностики предзвонков для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44896-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44896-103">_**Тема последнего изменения:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="44896-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="44896-104">Средство диагностики предварительных вызовов Lync (ПКД) — это клиентское приложение, позволяющее узнать, как текущее состояние сети может повлиять на качество звука при предстоящем звонке в корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="44896-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="44896-105">ПКД наиболее полезен в ситуациях, когда последний прыжок сети, скорее всего, является самым слабым (например, при наличии ноутбуков в общедоступной сети Wi-Fi или домашних пользователей).</span><span class="sxs-lookup"><span data-stu-id="44896-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="44896-106">ПКД создает небольшой потоковый пакет, который проходит по этому заключительному этапу сети.</span><span class="sxs-lookup"><span data-stu-id="44896-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="44896-107">Затем средство анализирует поток пакета, чтобы оценить, как нарушение и убытки в этой области могут повлиять на качество связи, а затем предоставляет отчет.</span><span class="sxs-lookup"><span data-stu-id="44896-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="44896-108">Вы можете запускать ПКД на клиенте постоянно, даже при помещении звонков.</span><span class="sxs-lookup"><span data-stu-id="44896-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="44896-109">Поток пакетов не оказывает существенного воздействия на пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="44896-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="44896-110">**Последний выпуск ПКД версии 1,1 включает следующие улучшения:**</span><span class="sxs-lookup"><span data-stu-id="44896-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="44896-111">Поддержка более длинных паролей, которые теперь могут содержать до 127 символов</span><span class="sxs-lookup"><span data-stu-id="44896-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="44896-112">Дополнительная диагностика проблем со входом для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="44896-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="44896-113">Улучшенная поддержка гибридных развертываний Lync</span><span class="sxs-lookup"><span data-stu-id="44896-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="44896-114">Обновления средства выбора учетных данных</span><span class="sxs-lookup"><span data-stu-id="44896-114">Updates to credential picker</span></span>

  - <span data-ttu-id="44896-115">Улучшенная стабильность</span><span class="sxs-lookup"><span data-stu-id="44896-115">Stability improvements</span></span>

<span data-ttu-id="44896-116">Благодарим за отзыв.</span><span class="sxs-lookup"><span data-stu-id="44896-116">We appreciate any feedback.</span></span> <span data-ttu-id="44896-117">Пожалуйста, отправляйте вопросы и ответы по вопросам поддержки по адресу <pcdfb@microsoft.com> [ПКД отзыва](mailto:pcdfb@microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="44896-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="44896-118">В этой статье содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="44896-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="44896-119">Версии ПКД для Lync</span><span class="sxs-lookup"><span data-stu-id="44896-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="44896-120">Требования к системе для Lync ПКД</span><span class="sxs-lookup"><span data-stu-id="44896-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="44896-121">Возможности Lync ПКД</span><span class="sxs-lookup"><span data-stu-id="44896-121">Lync PCD Features</span></span>

  - <span data-ttu-id="44896-122">Выполнение Lync ПКД</span><span class="sxs-lookup"><span data-stu-id="44896-122">Running Lync PCD</span></span>

  - <span data-ttu-id="44896-123">Удаление Lync ПКД</span><span class="sxs-lookup"><span data-stu-id="44896-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="44896-124">Версии ПКД для Lync</span><span class="sxs-lookup"><span data-stu-id="44896-124">Lync PCD Versions</span></span>

<span data-ttu-id="44896-125">В этой статье описаны следующие версии средства, которые можно загрузить бесплатно.</span><span class="sxs-lookup"><span data-stu-id="44896-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="44896-126">Классическое приложение для[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)Windows ()</span><span class="sxs-lookup"><span data-stu-id="44896-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="44896-127">Требования к системе для Lync ПКД</span><span class="sxs-lookup"><span data-stu-id="44896-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44896-128">Для ПКД требуется, чтобы веб-интерфейс единой системы обмена сообщениями (УКВА) был установлен и настроен для поддержки мобильных клиентов в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44896-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="44896-129">УКВА устанавливается вместе с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44896-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="44896-130">Требования для классических приложений для Windows</span><span class="sxs-lookup"><span data-stu-id="44896-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="44896-131">Любая версия операционной системы Windows 7 или Windows 8.</span><span class="sxs-lookup"><span data-stu-id="44896-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="44896-132">Microsoft .NET Framework 4,5, на котором можно найти по адресу[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="44896-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="44896-133">Возможности Lync ПКД</span><span class="sxs-lookup"><span data-stu-id="44896-133">Lync PCD Features</span></span>

<span data-ttu-id="44896-134">Lync ПКД включает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="44896-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="44896-135">Запускать по запросу (2-минутные пакеты)</span><span class="sxs-lookup"><span data-stu-id="44896-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="44896-136">Всегда запускать в режиме "включено" (до 24 часов в привязанном представлении)</span><span class="sxs-lookup"><span data-stu-id="44896-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="44896-137">Исторический вид тестовых запусков</span><span class="sxs-lookup"><span data-stu-id="44896-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="44896-138">Диагностика сбоев при входе (только Lync ПКД для Windows 8)</span><span class="sxs-lookup"><span data-stu-id="44896-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="44896-139">![Снимок экрана с индикатором выполнения входных компонентов Lync ПКД](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Снимок экрана с индикатором выполнения входных компонентов Lync ПКД")</span><span class="sxs-lookup"><span data-stu-id="44896-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="44896-140">Графическое представление метрик сети — сетевые MOS, потеря пакетов и нарушение колебаний в полноэкранном режиме и прикрепленном представлении.</span><span class="sxs-lookup"><span data-stu-id="44896-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="44896-141">**Полноэкранный режим**</span><span class="sxs-lookup"><span data-stu-id="44896-141">**Full screen view**</span></span>

<span data-ttu-id="44896-142">![Графики с результатами тестирования с помощью средства диагностики PreCall](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Графики с результатами тестирования с помощью средства диагностики PreCall")</span><span class="sxs-lookup"><span data-stu-id="44896-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="44896-143">**Привязанное представление**</span><span class="sxs-lookup"><span data-stu-id="44896-143">**Snapped view**</span></span>

<span data-ttu-id="44896-144">![Средство диагностики PreCall, результаты тестирования использования](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Средство диагностики PreCall, результаты тестирования использования")</span><span class="sxs-lookup"><span data-stu-id="44896-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="44896-145">Выполнение Lync ПКД</span><span class="sxs-lookup"><span data-stu-id="44896-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="44896-146">Запущен классическое приложение Windows</span><span class="sxs-lookup"><span data-stu-id="44896-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="44896-147">Чтобы запустить ПКД в системе Windows 7, в меню " **Пуск** " выберите пункт " **Диагностика перед вызовом** ".</span><span class="sxs-lookup"><span data-stu-id="44896-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="44896-148">Чтобы запустить ПКД в системе Windows 8, щелкните значок на начальном экране или выполните поиск по запросу "Диагностика для предзвонков".</span><span class="sxs-lookup"><span data-stu-id="44896-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="44896-149">![Значок средства диагностики PreCall](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Значок средства диагностики PreCall")</span><span class="sxs-lookup"><span data-stu-id="44896-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="44896-150">При запуске средства выберите предпочтительный способ предоставления учетных данных, а затем в диалоговом окне **Параметры средства диагностики** для подготовки к диагностике выберите команду " **ОК**".</span><span class="sxs-lookup"><span data-stu-id="44896-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="44896-151">Нажмите кнопку **начать проверку** , чтобы начать работу с диагностикой.</span><span class="sxs-lookup"><span data-stu-id="44896-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="44896-152">Если вы выбрали параметр **использовать сетевые учетные данные** , проверка начнется немедленно.</span><span class="sxs-lookup"><span data-stu-id="44896-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="44896-153">Если вы выбрали параметр **предоставить учетные данные** , откроется диалоговое окно " **Безопасность Windows** ".</span><span class="sxs-lookup"><span data-stu-id="44896-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="44896-154">После ввода учетных данных начинается проверка.</span><span class="sxs-lookup"><span data-stu-id="44896-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="44896-155">Удаление Lync ПКД</span><span class="sxs-lookup"><span data-stu-id="44896-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="44896-156">Чтобы удалить Lync ПКД, выполните действия, описанные в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="44896-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="44896-157">В системе Windows 7 откройте **Панель управления**, выберите " **программы и компоненты**", а затем дважды щелкните элемент "Диагностика предварительных **вызовов Lync 2013**".</span><span class="sxs-lookup"><span data-stu-id="44896-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="44896-158">В системе Windows 8 щелкните правой кнопкой мыши плитку ПКД и выберите команду **Удалить** на панели приложения в нижней части начального экрана.</span><span class="sxs-lookup"><span data-stu-id="44896-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

