---
title: Настройка основного сервера управления
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Сводка: Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2015.'
ms.openlocfilehash: a89ee8ca7c7f5601d9219ef49643adc2ebf99883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277673"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="511b3-103">Настройка основного сервера управления</span><span class="sxs-lookup"><span data-stu-id="511b3-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="511b3-104">**Сводка:** Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="511b3-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="511b3-105">Чтобы воспользоваться всеми преимуществами новых возможностей мониторинга работоспособности, включенных в Skype для бизнеса Server 2015, необходимо сначала назначить компьютер для работы в качестве основного сервера управления.</span><span class="sxs-lookup"><span data-stu-id="511b3-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="511b3-106">Затем необходимо установить System Center Operations Manager 2012 с пакетом обновления 1 (SP1) или R2 либо System Center Operations Manager 2007 R2 на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="511b3-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="511b3-107">Кроме того, необходимо сначала установить поддерживаемую версию SQL Server, которая будет выступать в качестве серверной базы данных Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="511b3-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="511b3-108">При установке System Center Operations Manager вам потребуется установить все компоненты этого продукта, в том числе следующие:</span><span class="sxs-lookup"><span data-stu-id="511b3-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="511b3-109">рабочую базу данных;</span><span class="sxs-lookup"><span data-stu-id="511b3-109">Operational database</span></span>

- <span data-ttu-id="511b3-110">Сервер</span><span class="sxs-lookup"><span data-stu-id="511b3-110">Server</span></span>

- <span data-ttu-id="511b3-111">консоль;</span><span class="sxs-lookup"><span data-stu-id="511b3-111">Console</span></span>

- <span data-ttu-id="511b3-112">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="511b3-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="511b3-113">веб-консоль;</span><span class="sxs-lookup"><span data-stu-id="511b3-113">Web console</span></span>

- <span data-ttu-id="511b3-114">отчеты;</span><span class="sxs-lookup"><span data-stu-id="511b3-114">Reporting</span></span>

- <span data-ttu-id="511b3-115">хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="511b3-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="511b3-116">Перед установкой System Center Operations Manager 2012 необходимо установить[распространяемый пакет Microsoft Report Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442).</span><span class="sxs-lookup"><span data-stu-id="511b3-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="511b3-117">Сведения об этих программах и их установке см. по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="511b3-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="511b3-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="511b3-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="511b3-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="511b3-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="511b3-120">Имейте в виду, что вы можете использовать только один корневой сервер управления для развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="511b3-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="511b3-121">Импорт пакетов управления Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="511b3-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="511b3-122">Вы можете расширять возможности System Center Operations Manager, устанавливая пакеты управления (программное обеспечение, которое определяет, какие элементы отслеживает диспетчер операций System Center Operations Manager), как эти элементы должны отслеживаться и как будут запускаться оповещения. отчета.</span><span class="sxs-lookup"><span data-stu-id="511b3-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="511b3-123">Skype для бизнеса Server 2015 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="511b3-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="511b3-124">**Пакет управления компонентом и пользовательским интерфейсом** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) отслеживает проблемы в Skype для бизнеса, записанные в журналах событий, регистрируются счетчиками производительности или записываются в записи сведений о вызовах (Кдрс) или в базы данных качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="511b3-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="511b3-125">Для устранения критических проблем можно настроить System Center Operations Manager для немедленного уведомления администраторов по электронной почте, мгновенным сообщениям или SMS-сообщениям.</span><span class="sxs-lookup"><span data-stu-id="511b3-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="511b3-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span><span class="sxs-lookup"><span data-stu-id="511b3-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="511b3-127">Дополнительные сведения о настройке уведомлений Operations Manager: [Настройка уведомлений](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="511b3-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="511b3-128">**Активный пакет управления мониторингом** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) заблаговременно проверяют ключевые компоненты сервера Skype для бизнеса, например вход в систему, Обмен мгновенными сообщениями и звонки на телефон, находящийся в коммутируемой телефонной сети с открытым подключением (КТСОП). ).</span><span class="sxs-lookup"><span data-stu-id="511b3-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="511b3-129">Такая проверка выполняется с помощью командлетов искусственных транзакций Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="511b3-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="511b3-130">Например, командлет **Test-CsIM** позволяет смоделировать сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="511b3-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="511b3-131">В случае сбоя при моделировании сеанса формируется оповещение.</span><span class="sxs-lookup"><span data-stu-id="511b3-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="511b3-p105">Одним из важнейших этапов является импорт пакетов управления. Если они не импортированы, в Skype для бизнеса Server невозможно наблюдать за событиями и выполнять искусственные транзакции с помощью Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="511b3-p105">Importing the management packs is a crucial step. If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="511b3-p106">Пакет управления компонентами и пользователями предназначен только для наблюдения в Skype для бизнеса Server 2015. Если одновременно установлены программы Skype для бизнеса Server 2015 и Lync Server 2013, следует по-прежнему пользоваться пакетами управления Lync Server 2013 для компьютеров Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="511b3-p106">The Component and User Management Pack is used to monitor only Skype for Business Server 2015. If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="511b3-136">К пакетам управления для Skype для бизнеса Server 2015 относятся пакет управления компонентами и пользователями Skype для бизнеса Server 2015 и пакет управления активным наблюдением Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="511b3-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="511b3-137">Для импорта пакетов управления можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="511b3-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="511b3-138">**System Center Operations Manager** С помощью этого метода вы можете добавить мониторинг для Skype для бизнеса Server с помощью Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="511b3-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="511b3-139">**Оболочка Operations Manager** С помощью консоли Operations Manager можно импортировать их напрямую или устранить проблемы, возникающие при импорте пакетов управления, используя консоль System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="511b3-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="511b3-140">Импорт пакетов управления с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="511b3-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="511b3-141">Загрузите файл SkypeForBusiness2015ManagementPacks.msi с веб-страницы загрузки Майкрософт и установите файл msi.</span><span class="sxs-lookup"><span data-stu-id="511b3-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="511b3-142">В System Center Operations Manager щелкните элемент **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="511b3-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="511b3-143">В области "Администрирование" щелкните правой кнопкой мыши **пакеты управления**и выберите пункт **Импорт пакетов управления**.</span><span class="sxs-lookup"><span data-stu-id="511b3-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="511b3-144">В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Добавить**, затем щелкните **Добавить с диска**.</span><span class="sxs-lookup"><span data-stu-id="511b3-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="511b3-145">В диалоговом окне **Подключение к каталогу в Интернете** щелкните **Нет**.</span><span class="sxs-lookup"><span data-stu-id="511b3-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="511b3-p107">В диалоговом окне **Выберите пакеты управления для импорта** найдите и выберите файлы Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp и Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, затем нажмите кнопку **Открыть**. Для выбора нескольких файлов в этом диалоговом окне щелкните первый файл, затем, удерживая нажатой клавишу Ctrl, щелкните последующие файлы.</span><span class="sxs-lookup"><span data-stu-id="511b3-p107">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**. To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="511b3-p108">В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Установить**. Сообщение об ошибке и сбой установки, как правило, указывают на то, что папка, в которой находятся файлы пакетов управления, защищена функцией контроля учетных записей Windows. В этом случае скопируйте файлы в другую папку и запустите процесс импорта и установки заново.</span><span class="sxs-lookup"><span data-stu-id="511b3-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="511b3-p109">В диалоговом окне **Выберите пакеты управления** нажмите кнопку **Закрыть**. Процесс импорта и установки может продолжаться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="511b3-p109">In the **Select Management Packs** dialog box, click **Close**. The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="511b3-153">Импорт пакетов управления с помощью оболочки Operations Manager</span><span class="sxs-lookup"><span data-stu-id="511b3-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="511b3-p110">Как правило, пакеты управления удобнее импортировать с консоли Operations Manager. Однако при возникновении ошибки и сбое импорта в консоли не всегда отображаются необходимые сведения об ошибке. В оболочке Operations Manager представлена более подробная информация. В случае неполадок при импорте пакета управления средствами Operations Manager импортируйте этот пакет с помощью оболочки Operations Manager. Информация, отображаемая в оболочке Operations Manager, позволяет определить причину сбоя импорта.</span><span class="sxs-lookup"><span data-stu-id="511b3-p110">In general, it is easier to import the management packs by using the Operations Manager console. However, if an error occurs and the import fails, the console does not always provide adequate error reports. By comparison, the Operations Manager Shell provides detailed information. If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell. The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="511b3-159">Нажмите кнопку **Пуск** и щелкните **Все программы**, **Microsoft System Center 2012**, **Operations Manager**, затем **Оболочка Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="511b3-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="511b3-160">В командной строке оболочке Operations Manager введите следующую команду, вставив реальный путь к копии файла Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, затем нажмите клавишу Enter:</span><span class="sxs-lookup"><span data-stu-id="511b3-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="511b3-161">После импорта первого пакета управления повторите процесс, указав путь к копии файла Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="511b3-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
