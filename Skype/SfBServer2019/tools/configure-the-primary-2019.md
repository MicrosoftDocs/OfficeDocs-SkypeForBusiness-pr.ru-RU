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
description: Сводка. Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2019.
ms.openlocfilehash: 872459f99f2e620d3d34db1196a8618476650c98
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806069"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="f9bf7-103">Настройка основного сервера управления</span><span class="sxs-lookup"><span data-stu-id="f9bf7-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="f9bf7-104">**Сводка:** Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="f9bf7-105">Чтобы в полной мере воспользоваться новыми возможностями мониторинга состояния, включенными в Skype для бизнеса Server 2019, необходимо сначала назначить компьютер для работы в качестве основного сервера управления.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="f9bf7-106">Затем на этом компьютере необходимо установить System Center Operations Manager 2012 с sp1 или R2 или System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="f9bf7-107">Кроме того, сначала необходимо установить поддерживаемую версию SQL Server, чтобы она функционировала как тыловая база данных Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="f9bf7-108">При установке System Center Operations Manager необходимо установить все компоненты этого продукта, в том числе:</span><span class="sxs-lookup"><span data-stu-id="f9bf7-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="f9bf7-109">рабочую базу данных;</span><span class="sxs-lookup"><span data-stu-id="f9bf7-109">Operational database</span></span>

- <span data-ttu-id="f9bf7-110">Server</span><span class="sxs-lookup"><span data-stu-id="f9bf7-110">Server</span></span>

- <span data-ttu-id="f9bf7-111">Консоль</span><span class="sxs-lookup"><span data-stu-id="f9bf7-111">Console</span></span>

- <span data-ttu-id="f9bf7-112">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9bf7-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="f9bf7-113">веб-консоль;</span><span class="sxs-lookup"><span data-stu-id="f9bf7-113">Web console</span></span>

- <span data-ttu-id="f9bf7-114">Отчётность</span><span class="sxs-lookup"><span data-stu-id="f9bf7-114">Reporting</span></span>

- <span data-ttu-id="f9bf7-115">хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9bf7-116">Перед установкой System Center Operations Manager 2012 необходимо установить распространяемый пакет "Microsoft[Report Viewer 2010".](https://www.microsoft.com/download/details.aspx?id=6442)</span><span class="sxs-lookup"><span data-stu-id="f9bf7-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="f9bf7-117">Подробные сведения об этих продуктах и их установке см. по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="f9bf7-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="f9bf7-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="f9bf7-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="f9bf7-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="f9bf7-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="f9bf7-120">Помните, что для каждого развертывания Skype для бизнеса Server может быть только один корневой сервер управления.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="f9bf7-121">Импорт пакетов управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="f9bf7-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="f9bf7-122">Вы можете расширить возможности System Center Operations Manager, установив пакеты управления — программное обеспечение, которое определяет, какие элементы System Center Operations Manager может отслеживать, как следует отслеживать эти элементы, а также как следует запускать оповещения и сообщать о них.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="f9bf7-123">Skype для бизнеса Server 2019 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="f9bf7-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="f9bf7-124"> Пакет управления компонентами и пользователями (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) отслеживает проблемы Skype для бизнеса Server, зарегистрированные в журналах событий, зарегистрированные счетчиками производительности или зарегистрированные в базах данных регистрации вызовов (CDRs) или качества обслуживания (QoE).</span><span class="sxs-lookup"><span data-stu-id="f9bf7-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="f9bf7-125">При критических проблемах System Center Operations Manager можно настроить для немедленного уведомления администраторов с помощью электронной почты, мгновенных сообщений или SMS-сообщений.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="f9bf7-126">(SMS или служба коротких сообщений — это технология, используемая для отправки текстовых сообщений с одного мобильного устройства на другое.)</span><span class="sxs-lookup"><span data-stu-id="f9bf7-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f9bf7-127">Подробные сведения о настройке уведомлений Operations Manager см. в [подстройки "Настройка уведомлений".](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="f9bf7-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="f9bf7-128">Пакет **управления active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) заблаговременно тестирует ключевые компоненты Skype для бизнеса Server, такие как вход в систему, обмен мгновенными сообщениями или звонки на телефон, расположенный в телефонной сети общего пользования (STN).</span><span class="sxs-lookup"><span data-stu-id="f9bf7-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="f9bf7-129">Эти тесты проводятся с помощью синтетического транзакции Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="f9bf7-130">Например, командлет **Test-CsIM** имитирует сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="f9bf7-131">Если эта имитация беседы не удалась, создается оповещение.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="f9bf7-132">Импорт пакетов управления является критически важным этапом.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="f9bf7-133">Если пакеты управления не импортировать, вы не сможете использовать Operations Manager для отслеживания событий Skype для бизнеса Server или запуска искусственных транзакций Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="f9bf7-134">Пакет управления компонентами и пользователями используется для отслеживания только Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="f9bf7-135">Если вы используете сценарий сосуществования, в котором установлены Skype для бизнеса Server 2019 и Skype для бизнеса Server 2015, следует продолжать использовать пакеты управления Skype для бизнеса Server 2015 для компьютеров Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="f9bf7-136">Пакеты управления для Skype для бизнеса Server 2019 включают пакеты управления компонентами и пользователями Skype для бизнеса Server 2019 и Skype для бизнеса Server 2019 Active Monitoring Management Pack.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="f9bf7-137">Для импорта пакетов управления можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="f9bf7-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="f9bf7-138">**System Center Operations Manager** С помощью этого метода operations Manager добавляет мониторинг для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="f9bf7-139">**Operations Manager Shell** С помощью оболочки Operations Manager можно импортировать напрямую или устранять неполадки, которые могут возникнуть при импорте пакетов управления с помощью консоли System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="f9bf7-140">Импорт пакетов управления с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="f9bf7-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="f9bf7-141">Скачайте SkypeForBusiness2019ManagementPacks.msi веб-загрузки Майкрософт и установите MSI.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="f9bf7-142">В System Center Operations Manager щелкните **"Администрирование".**</span><span class="sxs-lookup"><span data-stu-id="f9bf7-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="f9bf7-143">На панели Администрирование щелкните правой кнопкой **Пакеты управления** и выберите команду **Импорт пакетов управления**.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="f9bf7-144">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Добавить** и щелкните элемент **Add from disk** (Добавить с диска).</span><span class="sxs-lookup"><span data-stu-id="f9bf7-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="f9bf7-145">В **диалоговом окне "Подключение** к интернет-каталогу" нажмите кнопку **"Нет"**</span><span class="sxs-lookup"><span data-stu-id="f9bf7-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="f9bf7-146">В **диалоговом** окне "Выбор пакетов управления для импорта" найдите и выберите файлы, Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2019.Monitoring.ComponentAndUser.mp нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="f9bf7-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="f9bf7-147">Чтобы выбрать несколько файлов в диалоговом окне, щелкните первый файл, а затем удерживайте клавишу CTRL и щелкните последующие файлы.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="f9bf7-148">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="f9bf7-149">Если отображается сообщение об ошибке и установка завершается со сбоем, обычно это указывает на то, что файлы пакетов управления находятся в папке, защищенной функцией контроля учетных записей Windows.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="f9bf7-150">В этом случае скопируйте файлы в другую папку, а затем перезапустите процесс импорта и установки.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="f9bf7-151">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="f9bf7-152">Для завершения процесса импорта и установки может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="f9bf7-153">Импорт пакетов управления с помощью оболочки Operations Manager</span><span class="sxs-lookup"><span data-stu-id="f9bf7-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="f9bf7-154">В общем, проще импортировать пакеты управления с помощью консоли Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="f9bf7-155">Однако при ошибке и с ошибке импорта консоль не всегда предоставляет соответствующие отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="f9bf7-156">Для сравнения, в оболочке Operations Manager предоставляется подробная информация.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="f9bf7-157">Если вы используете Operations Manager и при импорте пакета управления столкнулись с проблемой, импортировать пакет с помощью оболочки Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="f9bf7-158">Сведения, предоставляемые в оболочке Operations Manager, помогут определить причину сбой импорта.</span><span class="sxs-lookup"><span data-stu-id="f9bf7-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="f9bf7-159">Нажмите **кнопку**"Начните", выберите "Все **программы", "Microsoft System Center 2012",** **"Operations Manager"** и **"Оболочка Operations Manager".** </span><span class="sxs-lookup"><span data-stu-id="f9bf7-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="f9bf7-160">В Командная команда Operations Manager введите следующую команду, используя фактический путь к копии файла Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="f9bf7-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="f9bf7-161">После импорта первого пакета управления повторите этот процесс, используя путь к копии файла Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="f9bf7-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
