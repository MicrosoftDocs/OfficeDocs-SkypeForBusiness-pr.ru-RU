---
title: Настройка основного сервера управления
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: Сводка. Настройка основного сервера управления, установка system Center Operations Manager и пакеты управления импортом для Skype для бизнеса Server 2015.
ms.openlocfilehash: ace25e1b4971c561dc1544290b04f481f36c9676
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111645"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="b998a-103">Настройка основного сервера управления</span><span class="sxs-lookup"><span data-stu-id="b998a-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="b998a-104">**Сводка:** Настройка основного сервера управления, установка диспетчера операций System Center и пакеты управления импортом для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b998a-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="b998a-105">Чтобы в полной мере воспользоваться новыми возможностями мониторинга состояния здоровья, включенными в Skype для бизнеса Server 2015, сначала необходимо назначить компьютер, который будет выступать в качестве основного сервера управления.</span><span class="sxs-lookup"><span data-stu-id="b998a-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="b998a-106">Затем необходимо установить диспетчер операций System Center 2012 SP1 или R2 или System Center Operations Manager 2007 R2 на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b998a-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="b998a-107">Кроме того, сначала необходимо установить поддерживаемую версию SQL Server, чтобы функционировать в качестве базы данных диспетчера операций.</span><span class="sxs-lookup"><span data-stu-id="b998a-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="b998a-108">При установке system Center Operations Manager необходимо установить все компоненты этого продукта, включая:</span><span class="sxs-lookup"><span data-stu-id="b998a-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="b998a-109">рабочую базу данных;</span><span class="sxs-lookup"><span data-stu-id="b998a-109">Operational database</span></span>

- <span data-ttu-id="b998a-110">Server</span><span class="sxs-lookup"><span data-stu-id="b998a-110">Server</span></span>

- <span data-ttu-id="b998a-111">Консоль</span><span class="sxs-lookup"><span data-stu-id="b998a-111">Console</span></span>

- <span data-ttu-id="b998a-112">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b998a-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="b998a-113">веб-консоль;</span><span class="sxs-lookup"><span data-stu-id="b998a-113">Web console</span></span>

- <span data-ttu-id="b998a-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="b998a-114">Reporting</span></span>

- <span data-ttu-id="b998a-115">хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="b998a-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b998a-116">Перед установкой System Center Operations Manager 2012 необходимо установить пакет "Microsoft[Report Viewer 2010".](https://www.microsoft.com/download/details.aspx?id=6442)</span><span class="sxs-lookup"><span data-stu-id="b998a-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="b998a-117">Сведения об этих продуктах и их установке см. в следующих ссылках:</span><span class="sxs-lookup"><span data-stu-id="b998a-117">For details about these products and their installation, see the following links:</span></span>

- <span data-ttu-id="b998a-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span><span class="sxs-lookup"><span data-stu-id="b998a-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span></span>

- [<span data-ttu-id="b998a-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="b998a-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="b998a-120">Имейте в виду, что на развертывание Skype для бизнес-сервера можно использовать только один сервер корневого управления.</span><span class="sxs-lookup"><span data-stu-id="b998a-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="b998a-121">Импорт пакетов управления Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b998a-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="b998a-122">Вы можете расширить возможности system Center Operations Manager путем установки пакетов управления — программного обеспечения, которое диктует, какие элементы system Center Operations Manager может отслеживать, как следует отслеживать эти элементы и как следует запускать и отчитаться о оповещениях.</span><span class="sxs-lookup"><span data-stu-id="b998a-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="b998a-123">Skype для бизнеса Server 2015 включает два пакета управления system Center Operations Manager, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="b998a-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="b998a-124"> Пакет управления компонентами и пользователями (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) отслеживает проблемы Skype для бизнес-сервера, записанные в журналах событий, зарегистрированных счетчиками производительности или войдите в записи детализации вызовов (CDRs) или базы данных качества работы (QoE).</span><span class="sxs-lookup"><span data-stu-id="b998a-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="b998a-125">В критически важных вопросах диспетчер операций центра систем может быть настроен для немедленного уведомления администраторов с помощью электронной почты, мгновенных сообщений или SMS-сообщений.</span><span class="sxs-lookup"><span data-stu-id="b998a-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="b998a-126">(SMS или служба коротких сообщений — это технология, используемая для отправки текстовых сообщений с одного мобильного устройства на другое.)</span><span class="sxs-lookup"><span data-stu-id="b998a-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b998a-127">Сведения о настройке уведомления диспетчера операций см. в [материале Configuring Notification.](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b998a-127">For details about configuring Operations Manager notification, see [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).</span></span>

- <span data-ttu-id="b998a-128">Пакет **управления** активным мониторингом (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) активно тестирует ключевые компоненты Skype для бизнес-сервера, такие как вход в систему, обмен мгновенными сообщениями или вызовы на телефон, расположенный в общедоступных телефонных сетях (PSTN).</span><span class="sxs-lookup"><span data-stu-id="b998a-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="b998a-129">Эти тесты проводятся с помощью синтетического комлета транзакций Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b998a-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="b998a-130">Например, командлет **Test-CsIM** имитирует сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="b998a-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="b998a-131">Если этот смоделированный разговор не удается, создается оповещение.</span><span class="sxs-lookup"><span data-stu-id="b998a-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="b998a-132">Импорт пакетов управления — это важный шаг.</span><span class="sxs-lookup"><span data-stu-id="b998a-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="b998a-133">Если пакеты управления не импортировать, вы не сможете использовать Operations Manager для мониторинга событий Skype для бизнеса Server или запуска синтетических транзакций Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="b998a-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="b998a-134">Пакет управления компонентами и пользователями используется для мониторинга только Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b998a-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2015.</span></span> <span data-ttu-id="b998a-135">Если вы находитесь в сценарии сосуществования, где установлены Skype для бизнеса Server 2015 и Lync Server 2013, необходимо продолжать использовать пакеты управления Lync Server 2013 для компьютеров Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b998a-135">If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="b998a-136">Пакеты управления для Skype для бизнеса Server 2015 включают компонент Skype для бизнес-сервера 2015 и пакет управления пользователями и пакет управления Skype для бизнеса Server 2015 Active Monitoring Management Pack.</span><span class="sxs-lookup"><span data-stu-id="b998a-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="b998a-137">Для импорта пакетов управления можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="b998a-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="b998a-138">**Диспетчер операций центра систем** С помощью этого метода диспетчер операций добавляет мониторинг для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b998a-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="b998a-139">**Shell диспетчера операций** Вы можете использовать консоль диспетчера операций для непосредственного импорта или устранения проблем, с которыми вы сталкиваетесь при импорте пакетов управления с помощью консоли System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b998a-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="b998a-140">Импорт пакетов управления с помощью диспетчера операций системного центра</span><span class="sxs-lookup"><span data-stu-id="b998a-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="b998a-141">Скачайте SkypeForBusiness2015ManagementPacks.msi из веб-загрузки Майкрософт и установите msi.</span><span class="sxs-lookup"><span data-stu-id="b998a-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="b998a-142">В диспетчере операций центра систем нажмите кнопку **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="b998a-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="b998a-143">На панели Администрирование щелкните правой кнопкой **Пакеты управления** и выберите команду **Импорт пакетов управления**.</span><span class="sxs-lookup"><span data-stu-id="b998a-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="b998a-144">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Добавить** и щелкните элемент **Add from disk** (Добавить с диска).</span><span class="sxs-lookup"><span data-stu-id="b998a-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="b998a-145">В **диалоговом окне Подключение** к каталогу в Интернете нажмите **кнопку Нет**.</span><span class="sxs-lookup"><span data-stu-id="b998a-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="b998a-146">В **диалоговом** окне Выберите пакеты управления для импорта, найдите и выберите файлы, Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, а затем нажмите **кнопку Открыть**.</span><span class="sxs-lookup"><span data-stu-id="b998a-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="b998a-147">Чтобы выбрать несколько файлов в диалоговом окне, нажмите первый файл, а затем удерживайте клавишу Ctrl и нажмите последующие файлы.</span><span class="sxs-lookup"><span data-stu-id="b998a-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="b998a-148">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="b998a-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="b998a-149">Если отображается сообщение об ошибке и установка завершается со сбоем, обычно это указывает на то, что файлы пакетов управления находятся в папке, защищенной функцией контроля учетных записей Windows.</span><span class="sxs-lookup"><span data-stu-id="b998a-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="b998a-150">В этом случае скопируйте файлы в другую папку и перезапустите процесс импорта и установки.</span><span class="sxs-lookup"><span data-stu-id="b998a-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="b998a-151">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b998a-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="b998a-152">Процесс импорта и установки может потребовать нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="b998a-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="b998a-153">Импорт пакетов управления с помощью оболочки диспетчера операций</span><span class="sxs-lookup"><span data-stu-id="b998a-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="b998a-154">В общем, проще импортировать пакеты управления с помощью консоли Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b998a-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="b998a-155">Однако при ошибке и сбой импорта консоль не всегда предоставляет соответствующие отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="b998a-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="b998a-156">Для сравнения, в Shell диспетчера операций предоставляется подробная информация.</span><span class="sxs-lookup"><span data-stu-id="b998a-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="b998a-157">Если вы используете диспетчер операций и при импорте пакета управления сталкиваются с проблемой, импортировать пакет с помощью shell диспетчера операций.</span><span class="sxs-lookup"><span data-stu-id="b998a-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="b998a-158">Сведения, предоставленные Shell диспетчера операций, помогут определить причину сбой импорта.</span><span class="sxs-lookup"><span data-stu-id="b998a-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="b998a-159">Нажмите **кнопку Начните,** щелкните Все **программы,** **нажмите кнопку Microsoft System Center 2012,** щелкните Диспетчер операций **и** нажмите **кнопку Диспетчер операций Shell**.</span><span class="sxs-lookup"><span data-stu-id="b998a-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="b998a-160">В командной команде введите следующую команду, используя фактический путь к копии файла Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="b998a-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="b998a-161">После импорта первого пакета управления повторите процесс, используя путь к копии файла Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="b998a-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```