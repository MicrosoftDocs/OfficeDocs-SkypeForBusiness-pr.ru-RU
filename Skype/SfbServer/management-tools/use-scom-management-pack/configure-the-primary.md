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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Сводка: Настройка основного сервера управления, установка System Center Operations Manager и импорт пакетов управления для Skype для бизнеса Server 2015.'
ms.openlocfilehash: 08c1967965248d26844433030e4bf77501882cd8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005964"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="046a1-103">Настройка основного сервера управления</span><span class="sxs-lookup"><span data-stu-id="046a1-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="046a1-104">**Сводка:** Настройте основной сервер управления, установите System Center Operations Manager и импортируйте пакеты управления для Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="046a1-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="046a1-105">Чтобы воспользоваться всеми преимуществами новых возможностей мониторинга работоспособности, включенных в Skype для бизнеса Server 2015, необходимо сначала назначить компьютер, который будет использоваться в качестве основного сервера управления.</span><span class="sxs-lookup"><span data-stu-id="046a1-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="046a1-106">После этого необходимо установить System Center Operations Manager 2012 с пакетом обновления 1 (SP1) или R2 или System Center Operations Manager 2007 R2 на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="046a1-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="046a1-107">Кроме того, необходимо сначала установить поддерживаемую версию SQL Server, чтобы она функционировала в качестве внутренней базы данных Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="046a1-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="046a1-108">При установке System Center Operations Manager вам потребуется установить все компоненты этого продукта, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="046a1-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="046a1-109">рабочую базу данных;</span><span class="sxs-lookup"><span data-stu-id="046a1-109">Operational database</span></span>

- <span data-ttu-id="046a1-110">Сервер</span><span class="sxs-lookup"><span data-stu-id="046a1-110">Server</span></span>

- <span data-ttu-id="046a1-111">Текстовое</span><span class="sxs-lookup"><span data-stu-id="046a1-111">Console</span></span>

- <span data-ttu-id="046a1-112">Командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="046a1-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="046a1-113">веб-консоль;</span><span class="sxs-lookup"><span data-stu-id="046a1-113">Web console</span></span>

- <span data-ttu-id="046a1-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="046a1-114">Reporting</span></span>

- <span data-ttu-id="046a1-115">хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="046a1-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="046a1-116">Перед установкой System Center Operations Manager 2012 необходимо установить[распространяемый пакет Microsoft Report Viewer 2010](https://www.microsoft.com/download/details.aspx?id=6442).</span><span class="sxs-lookup"><span data-stu-id="046a1-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="046a1-117">Подробные сведения об этих продуктах и их установке можно найти по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="046a1-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="046a1-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="046a1-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="046a1-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="046a1-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="046a1-120">Помните, что вы можете использовать только один корневой сервер управления для развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="046a1-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="046a1-121">Импорт пакетов управления Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="046a1-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="046a1-122">Возможности System Center Operations Manager можно расширить путем установки пакетов управления — программного обеспечения, которое определяет, какие элементы будут отслеживаться системой System Center Operations Manager, как эти элементы должны отслеживаться и как запускаются оповещения и регистрируют.</span><span class="sxs-lookup"><span data-stu-id="046a1-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="046a1-123">Skype для бизнеса Server 2015 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="046a1-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="046a1-124">**Пакет управления компонентом и пользователями** (Microsoft.ls.2015.Monitoring.ComponentAndUser.MP) отслеживает проблемы с Skype для бизнеса Server, зарегистрированные в журналах событий, зарегистрированные счетчиками производительности или зарегистрированные в журналах сведений о вызовах (CDRs) или в базах данных качества взаимодействия (QoE).</span><span class="sxs-lookup"><span data-stu-id="046a1-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="046a1-125">Для критических проблем можно настроить System Center Operations Manager для немедленного уведомления администраторов с помощью электронной почты, обмена мгновенными сообщениями или SMS.</span><span class="sxs-lookup"><span data-stu-id="046a1-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="046a1-126">(SMS или служба коротких сообщений) — это технология, используемая для отправки текстовых сообщений с одного мобильного устройства на другое.</span><span class="sxs-lookup"><span data-stu-id="046a1-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="046a1-127">Подробнее о настройке уведомлений Operations Manager можно узнать в статье [Настройка уведомлений](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="046a1-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="046a1-128">**Пакет управления активным мониторингом** (Microsoft.ls.2015.Monitoring.ActiveMonitoring.MP) проактивно тестирует основные компоненты Skype для бизнеса Server, например, вход в систему, Обмен мгновенными сообщениями и звонки на телефон, находящийся в телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="046a1-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="046a1-129">Эти тесты выполняются с помощью командлетов искусственной транзакции Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="046a1-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="046a1-130">Например, командлет **Test-CsIM** имитирует сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="046a1-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="046a1-131">При сбое имитации беседы создается оповещение.</span><span class="sxs-lookup"><span data-stu-id="046a1-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="046a1-132">Импорт пакетов управления является важнейшим действием.</span><span class="sxs-lookup"><span data-stu-id="046a1-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="046a1-133">Если пакеты управления не импортируются, вы не сможете использовать Operations Manager для мониторинга событий Skype для бизнеса Server или для выполнения искусственных транзакций Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="046a1-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="046a1-134">Пакет управления компонентом и пользователями используется для мониторинга только Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="046a1-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2015.</span></span> <span data-ttu-id="046a1-135">Если используется сценарий сосуществования, в котором установлены как Skype для бизнеса Server 2015, так и Lync Server 2013, следует по-прежнему использовать пакеты управления Lync Server 2013 для компьютеров Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="046a1-135">If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="046a1-136">Пакеты управления для Skype для бизнеса Server 2015 включают пакет управления сервером компонентов и пользователя Skype для бизнеса Server 2015 и пакет управления Skype для бизнеса Server 2015 Active Monitoring.</span><span class="sxs-lookup"><span data-stu-id="046a1-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="046a1-137">Для импорта пакетов управления можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="046a1-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="046a1-138">**System Center Operations Manager** С помощью этого метода можно добавить мониторинг для Skype для бизнеса Server с помощью Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="046a1-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="046a1-139">**Оболочка Operations Manager** С помощью командной консоли Operations Manager можно импортировать напрямую или устранять неполадки, возникающие при импорте пакетов управления с помощью консоли System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="046a1-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="046a1-140">Импорт пакетов управления с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="046a1-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="046a1-141">Скачайте файл SkypeForBusiness2015ManagementPacks. msi из веб-страниц загрузки Майкрософт и установите MSI.</span><span class="sxs-lookup"><span data-stu-id="046a1-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="046a1-142">В System Center Operations Manager щелкните **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="046a1-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="046a1-143">На панели Администрирование щелкните правой кнопкой **Пакеты управления** и выберите команду **Импорт пакетов управления**.</span><span class="sxs-lookup"><span data-stu-id="046a1-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="046a1-144">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Добавить** и щелкните элемент **Add from disk** (Добавить с диска).</span><span class="sxs-lookup"><span data-stu-id="046a1-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="046a1-145">В диалоговом окне **Подключение к каталогу в Интернете** нажмите кнопку **нет**.</span><span class="sxs-lookup"><span data-stu-id="046a1-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="046a1-146">В диалоговом окне **Выбор пакетов управления для импорта** найдите и выберите файлы Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp и Microsoft.ls.2015.Monitoring.ComponentAndUser.MP, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="046a1-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="046a1-147">Чтобы выбрать несколько файлов в диалоговом окне, щелкните первый файл, а затем, удерживая клавишу CTRL, щелкните следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="046a1-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="046a1-148">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="046a1-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="046a1-149">Если отображается сообщение об ошибке и установка завершается со сбоем, обычно это указывает на то, что файлы пакетов управления находятся в папке, защищенной функцией контроля учетных записей Windows.</span><span class="sxs-lookup"><span data-stu-id="046a1-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="046a1-150">Если это произойдет, скопируйте файлы в другую папку, а затем перезапустите процесс импорта и установки.</span><span class="sxs-lookup"><span data-stu-id="046a1-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="046a1-151">В диалоговом окне **Выбор пакетов управления** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="046a1-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="046a1-152">Для завершения процесса импорта и установки может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="046a1-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="046a1-153">Импорт пакетов управления с помощью командной консоли Operations Manager</span><span class="sxs-lookup"><span data-stu-id="046a1-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="046a1-154">В общем случае проще импортировать пакеты управления с помощью консоли Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="046a1-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="046a1-155">Однако при возникновении ошибки и неудачном импорте консоль не всегда предоставляет соответствующие отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="046a1-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="046a1-156">По сравнению с оболочкой Operations Manager предоставляются подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="046a1-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="046a1-157">Если вы используете Operations Manager и столкнулись с проблемами при импорте пакета управления, импортируйте пакет с помощью командной консоли Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="046a1-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="046a1-158">Сведения, предоставляемые оболочкой Operations Manager, помогут определить причину сбоя импорта.</span><span class="sxs-lookup"><span data-stu-id="046a1-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="046a1-159">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft System Center 2012**, **Operations Manager**, а затем — **Shell Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="046a1-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="046a1-160">В командной консоли Operations Manager введите в командной строке следующую команду, используя фактический путь к копии файла Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="046a1-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="046a1-161">После импорта первого пакета управления повторите этот процесс, указав путь к копии файла Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span><span class="sxs-lookup"><span data-stu-id="046a1-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
