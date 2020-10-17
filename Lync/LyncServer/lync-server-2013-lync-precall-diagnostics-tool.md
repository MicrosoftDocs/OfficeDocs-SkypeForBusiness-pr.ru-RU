---
title: 'Lync Server 2013: средство диагностики предзвонков для Lync'
description: 'Lync Server 2013: средство диагностики предзвонков для Lync.'
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
ms.openlocfilehash: 17c2c51551fe0991eb354a628b1d4660baa1532b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571995"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="86c5e-103">Средство диагностики предзвонков для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86c5e-103">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86c5e-104">_**Последнее изменение темы:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="86c5e-104">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="86c5e-105">Средство диагностики предварительных вызовов Lync (PCD) — это клиентское приложение, которое позволяет увидеть, как текущее состояние сети может повлиять на качество звука в предстоящем голосовом звонке предприятия.</span><span class="sxs-lookup"><span data-stu-id="86c5e-105">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="86c5e-106">PCD наиболее полезен в ситуациях, когда последний транзит сети скорее всего самый слабый (например, с ноутбуками в общедоступной сети Wi-Fi или для домашних пользователей).</span><span class="sxs-lookup"><span data-stu-id="86c5e-106">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="86c5e-107">PCD создает небольшой пакетный поток, который выполняет обход этого последнего участка сети.</span><span class="sxs-lookup"><span data-stu-id="86c5e-107">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="86c5e-108">Затем средство анализирует поток пакета для оценки того, как колебание и убытки по этому принципу могут повлиять на качество звонков, а затем предоставляет отчет.</span><span class="sxs-lookup"><span data-stu-id="86c5e-108">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="86c5e-109">PCD можно непрерывно запускать на клиенте, даже при размещается вызовов.</span><span class="sxs-lookup"><span data-stu-id="86c5e-109">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="86c5e-110">Поток пакета не оказывает существенного влияние на пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="86c5e-110">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="86c5e-111">**Последний выпуск PCD версии 1,1 содержит следующие усовершенствованные возможности:**</span><span class="sxs-lookup"><span data-stu-id="86c5e-111">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="86c5e-112">Поддержка более длинных паролей, которые теперь могут содержать до 127 символов</span><span class="sxs-lookup"><span data-stu-id="86c5e-112">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="86c5e-113">Дополнительная диагностика проблем с входом в систему проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="86c5e-113">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="86c5e-114">Улучшенная поддержка гибридных развертываний Lync</span><span class="sxs-lookup"><span data-stu-id="86c5e-114">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="86c5e-115">Обновление средства выбора учетных данных</span><span class="sxs-lookup"><span data-stu-id="86c5e-115">Updates to credential picker</span></span>

  - <span data-ttu-id="86c5e-116">Улучшения стабильности</span><span class="sxs-lookup"><span data-stu-id="86c5e-116">Stability improvements</span></span>

<span data-ttu-id="86c5e-117">Мы ценим ваши отзывы.</span><span class="sxs-lookup"><span data-stu-id="86c5e-117">We appreciate any feedback.</span></span> <span data-ttu-id="86c5e-118">Отправьте все вопросы по поддержке или проблемы в псевдоним [отзывов PCD](mailto:pcdfb@microsoft.com) по адресу <pcdfb@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="86c5e-118">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="86c5e-119">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="86c5e-119">This topic includes the following sections:</span></span>

  - <span data-ttu-id="86c5e-120">Версии PCD для Lync</span><span class="sxs-lookup"><span data-stu-id="86c5e-120">Lync PCD Versions</span></span>

  - <span data-ttu-id="86c5e-121">Требования к системе для Lync PCD</span><span class="sxs-lookup"><span data-stu-id="86c5e-121">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="86c5e-122">Функции Lync PCD</span><span class="sxs-lookup"><span data-stu-id="86c5e-122">Lync PCD Features</span></span>

  - <span data-ttu-id="86c5e-123">Запуск Lync PCD</span><span class="sxs-lookup"><span data-stu-id="86c5e-123">Running Lync PCD</span></span>

  - <span data-ttu-id="86c5e-124">Удаление Lync PCD</span><span class="sxs-lookup"><span data-stu-id="86c5e-124">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="86c5e-125">Версии PCD для Lync</span><span class="sxs-lookup"><span data-stu-id="86c5e-125">Lync PCD Versions</span></span>

<span data-ttu-id="86c5e-126">В этом разделе описываются следующие версии средства, доступные для бесплатной загрузки:</span><span class="sxs-lookup"><span data-stu-id="86c5e-126">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="86c5e-127">Классическое приложение Windows ( [https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914) )</span><span class="sxs-lookup"><span data-stu-id="86c5e-127">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="86c5e-128">Требования к системе для Lync PCD</span><span class="sxs-lookup"><span data-stu-id="86c5e-128">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86c5e-129">Для PCD необходимо установить и настроить веб-API объединенных коммуникаций (UCWA) для поддержки мобильных клиентов в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86c5e-129">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="86c5e-130">UCWA устанавливается вместе с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86c5e-130">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="86c5e-131">Требования к классическому приложению Windows</span><span class="sxs-lookup"><span data-stu-id="86c5e-131">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="86c5e-132">Любой выпуск операционной системы Windows 7 или Windows 8</span><span class="sxs-lookup"><span data-stu-id="86c5e-132">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="86c5e-133">Microsoft .NET Framework 4,5 доступен по адресу [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="86c5e-133">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="86c5e-134">Функции Lync PCD</span><span class="sxs-lookup"><span data-stu-id="86c5e-134">Lync PCD Features</span></span>

<span data-ttu-id="86c5e-135">Lync PCD включает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="86c5e-135">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="86c5e-136">Запускать по запросу по требованию (2-минутные пакеты)</span><span class="sxs-lookup"><span data-stu-id="86c5e-136">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="86c5e-137">Режим "всегда включено" (с привязанным режимом до 24 часов)</span><span class="sxs-lookup"><span data-stu-id="86c5e-137">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="86c5e-138">Исторический вид тестовых запусков</span><span class="sxs-lookup"><span data-stu-id="86c5e-138">Historical view of your test runs</span></span>

  - <span data-ttu-id="86c5e-139">Диагностика неудачных попыток входа (только Lync PCD для Windows 8)</span><span class="sxs-lookup"><span data-stu-id="86c5e-139">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="86c5e-140">![Снимок экрана с ходом выполнения входа в Lync PCD](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Снимок экрана с ходом выполнения входа в Lync PCD")</span><span class="sxs-lookup"><span data-stu-id="86c5e-140">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="86c5e-141">Графическое представление метрик сети — сетевой MOS, потери пакетов и колебаний колебаний в полноэкранном режиме и в привязанном виде.</span><span class="sxs-lookup"><span data-stu-id="86c5e-141">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="86c5e-142">**Полноэкранный режим**</span><span class="sxs-lookup"><span data-stu-id="86c5e-142">**Full screen view**</span></span>

<span data-ttu-id="86c5e-143">![Графы результатов проверки с помощью средства диагностики](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Графы результатов проверки с помощью средства диагностики")</span><span class="sxs-lookup"><span data-stu-id="86c5e-143">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="86c5e-144">**Привязанное представление**</span><span class="sxs-lookup"><span data-stu-id="86c5e-144">**Snapped view**</span></span>

<span data-ttu-id="86c5e-145">![Результаты проверки использования средства диагностики для отзыва](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Результаты проверки использования средства диагностики для отзыва")</span><span class="sxs-lookup"><span data-stu-id="86c5e-145">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="86c5e-146">Запуск Lync PCD</span><span class="sxs-lookup"><span data-stu-id="86c5e-146">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="86c5e-147">Запуск классического приложения Windows</span><span class="sxs-lookup"><span data-stu-id="86c5e-147">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="86c5e-148">Чтобы запустить PCD в системе Windows 7, выберите команду " **Диагностика вызовов** " в меню " **Пуск** ".</span><span class="sxs-lookup"><span data-stu-id="86c5e-148">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="86c5e-149">Чтобы запустить PCD в системе Windows 8, нажмите значок на начальном экране или выполните поиск по запросу "Диагностика до вызова".</span><span class="sxs-lookup"><span data-stu-id="86c5e-149">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="86c5e-150">![Значок средства диагностики перед вызовом](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Значок средства диагностики перед вызовом")</span><span class="sxs-lookup"><span data-stu-id="86c5e-150">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="86c5e-151">При запуске средства выберите предпочтительный способ предоставления учетных данных и выберите режим работы сети в диалоговом окне **Параметры средства диагностики перед вызовом** , а затем нажмите кнопку **ОК**:</span><span class="sxs-lookup"><span data-stu-id="86c5e-151">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="86c5e-152">Нажмите кнопку **начать проверку** , чтобы начать выполнение диагностики.</span><span class="sxs-lookup"><span data-stu-id="86c5e-152">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="86c5e-153">Если вы выбрали параметр **использовать сетевые учетные данные** , тест начнется немедленно.</span><span class="sxs-lookup"><span data-stu-id="86c5e-153">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="86c5e-154">Если выбран параметр **Разрешить ввод учетных данных** , откроется диалоговое окно " **Безопасность Windows** ".</span><span class="sxs-lookup"><span data-stu-id="86c5e-154">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="86c5e-155">После ввода учетных данных тест начнется.</span><span class="sxs-lookup"><span data-stu-id="86c5e-155">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="86c5e-156">Удаление Lync PCD</span><span class="sxs-lookup"><span data-stu-id="86c5e-156">Uninstalling Lync PCD</span></span>

<span data-ttu-id="86c5e-157">Чтобы удалить Lync PCD, выполните процедуру, описанную в операционной системе:</span><span class="sxs-lookup"><span data-stu-id="86c5e-157">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="86c5e-158">В системе Windows 7 откройте **Панель управления**, выберите пункт **программы и компоненты**, а затем дважды щелкните элемент Диагностика предварительных **вызовов Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="86c5e-158">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="86c5e-159">В системе Windows 8 щелкните правой кнопкой мыши плитку PCD и выберите **Удалить** на панели приложения в нижней части начального экрана.</span><span class="sxs-lookup"><span data-stu-id="86c5e-159">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

