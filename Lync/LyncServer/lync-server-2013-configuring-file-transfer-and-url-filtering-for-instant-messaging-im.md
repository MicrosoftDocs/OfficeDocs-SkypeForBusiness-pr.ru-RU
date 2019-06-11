---
title: Настройка фильтрации передачи файлов и URL-адресов для обмена мгновенными сообщениями (IM)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a><span data-ttu-id="e5ccc-102">Настройка фильтрации файлов и URL-адресов для обмена мгновенными сообщениями (IM) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5ccc-102">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5ccc-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e5ccc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e5ccc-104">Инструмент интеллектуального фильтра мгновенных сообщений помогает защитить развертывание Lync Server 2013 от распространения наиболее распространенных форм вирусов с минимальным снижением качества для взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-104">The Intelligent IM Filter tool helps protect your Lync Server 2013 deployment against the spread of the most common forms of viruses with minimal degradation to the user experience.</span></span> <span data-ttu-id="e5ccc-105">Используйте интеллектуальный фильтр мгновенных сообщений для настройки фильтров, чтобы блокировать непредусмотренные или потенциально опасные мгновенные сообщения от неизвестных конечных точек за пределами корпоративного брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-105">Use Intelligent IM Filter to configure filters to block unsolicited or potentially harmful instant messages from unknown endpoints outside the corporate firewall.</span></span> <span data-ttu-id="e5ccc-106">Вы можете настроить фильтры, указав условия, которые будут использоваться для определения того, что следует блокировать (например, мгновенные сообщения, содержащие гиперссылки с определенными префиксами и файлами с определенными расширениями).</span><span class="sxs-lookup"><span data-stu-id="e5ccc-106">You configure filters by specifying the criteria to be used to determine what should be blocked, such as instant messages containing hyperlinks with specific prefixes and files with specific extensions.</span></span>

<span data-ttu-id="e5ccc-107">Интеллектуальный фильтр мгновенных сообщений предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="e5ccc-107">Intelligent IM Filter provides the following:</span></span>

  - <span data-ttu-id="e5ccc-108">Улучшенная фильтрация URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-108">Enhanced URL filtering.</span></span>

  - <span data-ttu-id="e5ccc-109">Улучшенная фильтрация передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-109">Enhanced file transfer filtering.</span></span>

<span data-ttu-id="e5ccc-110">Настройка интеллектуального фильтра мгновенных сообщений включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="e5ccc-110">Configuring Intelligent IM Filter includes the following:</span></span>

  - <span data-ttu-id="e5ccc-111">Настройка фильтрации URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-111">Configuring URL filtering.</span></span>

  - <span data-ttu-id="e5ccc-112">Настройка фильтрации передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-112">Configuring file transfer filtering.</span></span>

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a><span data-ttu-id="e5ccc-113">Применение параметров фильтрации к мгновенным сообщениям</span><span class="sxs-lookup"><span data-stu-id="e5ccc-113">How Filtering Options Are Applied to Instant Messages</span></span>

<span data-ttu-id="e5ccc-114">Прежде чем развертывать инструмент интеллектуального фильтра сообщений, необходимо понять, как будут применяться параметры фильтрации, так как сообщения пересылаются с одного сервера Lync Server 2013 на другой.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-114">Before you deploy the Intelligent IM Message Filter tool, you need to understand how filtering options are applied as messages are routed from one Lync Server 2013 server to another.</span></span> <span data-ttu-id="e5ccc-115">Способ применения этих параметров фильтрации одинаков, независимо от того, находятся ли серверы в одной организации или на разных организационных границах.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-115">The way these filtering options are applied is consistent, regardless of whether the servers are located in a single organization or across organizational boundaries.</span></span> <span data-ttu-id="e5ccc-116">Это соответствие распространяется на то, как настроенные тексты уведомлений и предупреждений вставляются в сообщения и отправляются на другие серверы.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-116">This consistency applies to the way that the customized notice and warning texts are inserted into messages and sent across servers.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e5ccc-117">Фильтр мгновенных сообщений увеличивает объем ресурсов ЦП, необходимых для обработки URL-адресов в сообщении.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-117">The instant message filter increases the amount of CPU resources required to process URLs in a message.</span></span> <span data-ttu-id="e5ccc-118">Это повышение спроса на ЦП также влияет на производительность сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-118">This increase in CPU demand also affects the performance of Lync Server.</span></span>



</div>

<span data-ttu-id="e5ccc-119">С помощью страницы **фильтра URL-адреса** в группе " **мгновенные сообщения и присутствие** " на панели управления Lync Server вы можете заблокировать некоторые или все гиперссылки или настроить предупреждение.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-119">By using the **URL Filter** page in the **IM and Presence** group in Lync Server Control Panel, you can block some or all hyperlinks or configure a warning.</span></span> <span data-ttu-id="e5ccc-120">Предупреждение будет вставлено в начало мгновенного сообщения, которое содержит гиперссылку, если вы выбрали параметр **префикс** гиперссылки **Отправить сообщение**с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-120">The warning is inserted at the beginning of an instant message that contains a hyperlink when you choose the **Hyperlink prefix** option **Send warning message**.</span></span>

<span data-ttu-id="e5ccc-121">Если мгновенное сообщение передается с одного сервера на другой, применяются следующие общие правила.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-121">When an instant message travels from one server to another, the following general guidelines apply:</span></span>

  - <span data-ttu-id="e5ccc-122">Если сервер блокирует мгновенное сообщение (так как вы установили флажок **блокировать URL-адреса с расширением файла** на странице **фильтра URL-адреса** или если вы выбрали параметр **префикс гиперссылки** ), будет возвращено сообщение об ошибке. \*\*\*\* клиент.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-122">If a server blocks an instant message (because you selected the **Block URLs with file extension** check box on the **URL Filter** page or because you chose the **Hyperlink prefix** option **Block hyperlinks**), an error message is returned to the client.</span></span> <span data-ttu-id="e5ccc-123">Последующие серверы не получают это мгновенное сообщение.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-123">Subsequent servers do not receive this instant message.</span></span>

  - <span data-ttu-id="e5ccc-124">Если сервер (Server1) добавляет предупреждение в мгновенное сообщение, содержащее активную гиперссылку, последующий сервер (Server2), получающий это мгновенное сообщение, по-прежнему может выполнять различные действия на основе этой активной гиперссылки в мгновенных сообщениях и блокировать Мгновенное сообщение или добавление предупреждения.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-124">If a server (Server1) adds a warning to an instant message that contains an active hyperlink, a subsequent server (Server2) that receives this instant message can still take a different action based on this active hyperlink present in the instant message and block the instant message or add a warning.</span></span> <span data-ttu-id="e5ccc-125">Если Server2 настроен только на добавление предупреждений для этого URL-адреса, то предыдущее предупреждение, добавленное с помощью Server1, удаляется, а предупреждение, настроенное на Server2, добавляется в начало мгновенного сообщения.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-125">If Server2 is configured only to add a warning for this URL, the earlier warning added by Server1 is removed, and the warning configured on Server2 is added to the beginning of the instant message.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e5ccc-126">Если на компьютере установлено приложение Lync Server 2013 в смешанной среде, то для использования интеллектуального фильтра мгновенных сообщений требуется минимальная версия сервера Live Communications Server 2005 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="e5ccc-126">If you are running Lync Server 2013 in a mixed environment, Live Communications Server 2005 with SP1 is the minimum version required to use the Intelligent IM Filter application.</span></span> <span data-ttu-id="e5ccc-127">Интеллектуальный фильтр для обмена мгновенными сообщениями не поддерживается на сервере Live Communications Server 2005 без пакета обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="e5ccc-127">The Intelligent IM Filter is not supported on Live Communications Server 2005 without SP1.</span></span>



</div>

<div>

## <a name="url-filtering"></a><span data-ttu-id="e5ccc-128">Фильтрация URL-адресов</span><span class="sxs-lookup"><span data-stu-id="e5ccc-128">URL Filtering</span></span>

<span data-ttu-id="e5ccc-129">URL-адреса фильтруются в соответствии с префиксом гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-129">URLs are filtered according to their hyperlink prefix.</span></span> <span data-ttu-id="e5ccc-130">Ниже приведены примеры допустимых префиксов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-130">The following examples are valid prefixes:</span></span>

  - <span data-ttu-id="e5ccc-131">www\*.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-131">www\*.</span></span>

  - <span data-ttu-id="e5ccc-132">адреса.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-132">ftp.</span></span>

  - <span data-ttu-id="e5ccc-133">через</span><span class="sxs-lookup"><span data-stu-id="e5ccc-133">http:</span></span>

<span data-ttu-id="e5ccc-134">Если вы не настраиваете фильтр мгновенных сообщений для фильтрации URL-адресов, все URL-адреса, содержащиеся в мгновенных сообщениях, будут передаваться без изменений с сервера.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-134">If you do not configure the instant message filter to perform any URL filtering, all URLs contained in instant messages are passed unmodified through the server.</span></span> <span data-ttu-id="e5ccc-135">Если настроить фильтр мгновенных сообщений для фильтрации URL-адресов, URL-адреса в мгновенных сообщениях фильтруются в соответствии с параметрами, выбранными в диалоговом окне **Изменение фильтра URL-адреса** или **фильтра по новому URL-адресу** .</span><span class="sxs-lookup"><span data-stu-id="e5ccc-135">If you configure the instant message filter to perform URL filtering, URLs in instant messages are filtered according to the options that you select in the **Edit URL Filter** or **New URL Filter** dialog box.</span></span>

  - <span data-ttu-id="e5ccc-136">**Включить фильтр**   URL-адресов этот параметр позволяет применять фильтрацию URL-адресов для глобального развертывания или для выбранного сайта.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-136">**Enable URL filter**   This option enables URL filtering for the global deployment or for the site that you select.</span></span>

  - <span data-ttu-id="e5ccc-137">**Заблокируйте URL-адреса с помощью расширения**   . фильтр мгновенных сообщений блокирует любой активный URL-адрес в интрасети или Интернете, содержащий файл с расширением, указанным в поле **расширения типа файлов** , которое будет заблокировано в диалоговом окне **Изменение фильтра файлов** .</span><span class="sxs-lookup"><span data-stu-id="e5ccc-137">**Block URLs with file extension**   The instant message filter blocks any active intranet or Internet URL that contains a file with an extension listed under **File type extensions to block** in the **Edit File Filter** dialog box.</span></span> <span data-ttu-id="e5ccc-138">Если URL-адрес заблокирован, для отправителя выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-138">When a URL is blocked, an error message is displayed to the sender.</span></span> <span data-ttu-id="e5ccc-139">Если установлен этот флажок, этот параметр имеет приоритет над всеми остальными параметрами фильтрации для всех расширений файлов, определенных в разделе **расширения типа файла для блокировки**.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-139">When selected, this option takes precedence over all other filtering options for any file extensions defined under **File type extensions to block**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e5ccc-140">Фильтрация расширений файлов ограничена стандартными именами файлов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-140">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="e5ccc-141">Фильтрация не работает с расширениями файлов, внедренными в другие имена.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-141">Filtering may not work with file extensions embedded in other names.</span></span>

    
    </div>

<span data-ttu-id="e5ccc-142">Чтобы настроить способ обработки гиперссылок в текстовых беседах, выберите один из следующих параметров в разделе **префикс гиперссылки**:</span><span class="sxs-lookup"><span data-stu-id="e5ccc-142">To configure how hyperlinks are handled in instant message conversations, select one of the following options under **Hyperlink prefix**:</span></span>

  - <span data-ttu-id="e5ccc-143">**Не фильтруйте**   URL-адреса в сообщениях, отправляются с сервера.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-143">**Do not filter**   URLs in messages are sent through the server.</span></span> <span data-ttu-id="e5ccc-144">Если выбрать этот параметр, появится диалоговое окно **Разрешить сообщение** .</span><span class="sxs-lookup"><span data-stu-id="e5ccc-144">When you choose this option, the **Allow message** box appears.</span></span> <span data-ttu-id="e5ccc-145">В диалоговом окне **Разрешить введите текст** уведомления, которое вы хотите вставить в начало каждого мгновенного сообщения, содержащего гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-145">In the **Allow message** box, specify the notice that you want to insert at the beginning of each instant message containing hyperlinks.</span></span> <span data-ttu-id="e5ccc-146">Это уведомление может состоять не более чем из 65535 знаков.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-146">This notice can consist of no more than 65535 characters.</span></span>

  - <span data-ttu-id="e5ccc-147">**Блокировать гиперссылки**   . Доставка мгновенных сообщений с активными гиперссылками блокируется сервером Lync Server, а отправителю выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-147">**Block hyperlinks**   Delivery of instant messages containing active hyperlinks is blocked by Lync Server, and an error message is displayed to the sender.</span></span>

  - <span data-ttu-id="e5ccc-148">**Отправить предупреждение**   в Lync Server разрешены активные гиперссылки в мгновенных сообщениях, но это сообщение содержит предупреждение.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-148">**Send warning message**   Lync Server permits active hyperlinks in instant messages, but it includes a warning.</span></span> <span data-ttu-id="e5ccc-149">При выборе этого параметра появится окно **сообщения** с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-149">When you choose this option, the **Warning message** box appears.</span></span> <span data-ttu-id="e5ccc-150">В диалоговом окне **предупреждение** необходимо ввести предупреждение, которое вы хотите включить в мгновенные сообщения, содержащие действительные гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-150">In the **Warning message** box, you must type the warning that you want to include with instant messages containing valid hyperlinks.</span></span> <span data-ttu-id="e5ccc-151">Например, это предупреждение может выдать список возможных опасностей выбора неизвестной ссылки или ссылаться на нужные политики и требования вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-151">For example, this warning might state the potential dangers of clicking an unknown link, or it might refer to your organization’s relevant policies and requirements.</span></span> <span data-ttu-id="e5ccc-152">Предупреждение может состоять не более чем из 65535 символов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-152">The warning can be no more than 65535 characters.</span></span>

<span data-ttu-id="e5ccc-153">Если выбрать команду **блокировать гиперссылки** или **Отправить предупреждение**, будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e5ccc-153">If you select **Block hyperlinks** or **Send warning message**, the following options are available:</span></span>

  - <span data-ttu-id="e5ccc-154">**Исключить локальную интрасеть гиперссылки**   . фильтр мгновенных сообщений блокирует только URL-адреса в Интернете.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-154">**Exclude local intranet hyperlinks**   The instant message filter blocks only Internet URLs.</span></span> <span data-ttu-id="e5ccc-155">URL-адреса для расположений в интрасети передаются без изменений с сервера.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-155">URLs for locations within your intranet are passed unmodified through the server.</span></span> <span data-ttu-id="e5ccc-156">Тем не менее URL-адреса в интрасети, на которых работают индивидуальные серверы Lync Server, зависят от того, какие типы локальных сайтов считаются частью своей зоны интрасети.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-156">However, the intranet URLs that individual servers running Lync Server pass depend on which types of local websites are considered part of their intranet zone.</span></span> <span data-ttu-id="e5ccc-157">Чтобы проверить параметры зоны интрасети сервера, в разделе "Настройка параметров интрасети в Internet Explorer" [измените фильтр URL-адресов по умолчанию в Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).</span><span class="sxs-lookup"><span data-stu-id="e5ccc-157">To check a server’s intranet zone settings, see the “To configure your intranet settings in Internet Explorer” procedure in [Modify the default URL filter in Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md).</span></span>

  - <span data-ttu-id="e5ccc-158">**Отфильтруйте эти префиксы**   гиперссылок, чтобы выбрать, какие префиксы нужно заблокировать, нажмите кнопку **выбрать**, а затем в списке **выберите префикс гиперссылки**добавьте префиксы в список префиксов **гиперссылок** .</span><span class="sxs-lookup"><span data-stu-id="e5ccc-158">**Filter these hyperlink prefixes**   To choose which prefixes you want to block, click **Select**, and then, in **Select Hyperlink Prefix**, add the prefixes to the **Hyperlink prefixes** list.</span></span>
    
    <span data-ttu-id="e5ccc-159">Все префиксы, кроме **href** , должны заканчиваться точкой или двоеточием или звездочкой, за которой следует точка.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-159">All prefixes except **href** must end with a period or a colon, or an asterisk followed by a period.</span></span> <span data-ttu-id="e5ccc-160">Допустимые префиксы могут содержать символы из набора допустимых URL-знаков, кроме звездочки\*().</span><span class="sxs-lookup"><span data-stu-id="e5ccc-160">Valid prefixes can contain any characters in the set of valid URL characters except the asterisk (\*).</span></span> <span data-ttu-id="e5ccc-161">Набор допустимых символов URL-адреса: \# \*+/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` абкдефгхижклмнопкрстуввксиз | ~</span><span class="sxs-lookup"><span data-stu-id="e5ccc-161">The set of valid URL characters is: \#\*+/0123456789=@ABCDEFGHIJKLMNOPQRSTUVWXYZ^\_\` abcdefghijklmnopqrstuvwxyz|~</span></span>

</div>

<div>

## <a name="file-transfer-filtering"></a><span data-ttu-id="e5ccc-162">Фильтрация передачи файлов</span><span class="sxs-lookup"><span data-stu-id="e5ccc-162">File Transfer Filtering</span></span>

<span data-ttu-id="e5ccc-163">Фильтрация передаваемых фильтров влияет на мгновенные сообщения и конференции.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-163">Filter transfer filtering affects both instant messages and conferences.</span></span> <span data-ttu-id="e5ccc-164">Для конференций эти параметры влияют на функцию раздаточных материалов в клиенте Office Live Meeting 2007 и в средствах воспроизведения мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-164">For conferences, these settings affect the handout feature in the Office Live Meeting 2007 client and multimedia playback features.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e5ccc-165">Lync Server также включает параметры настройки передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-165">Lync Server also offers file transfer setting options.</span></span> <span data-ttu-id="e5ccc-166">Этот параметр на стороне сервера предлагается в дополнение к элементам управления на стороне клиента, доступным в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-166">This server-side option is offered in addition to the client-side controls available in Lync Server.</span></span>



</div>

<span data-ttu-id="e5ccc-167">Вы можете отфильтровать передачу файлов в текстовых беседах, когда вы используете функцию выдач в клиенте Office Live Meeting 2007 и для воспроизведения мультимедиа для всех типов файлов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-167">You can filter file transfers during instant message conversations, when you are using the handout feature in the Office Live Meeting 2007 client, and for multimedia playback features for all file types.</span></span> <span data-ttu-id="e5ccc-168">Для управления передачей файлов можно настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e5ccc-168">You can set the following options to control file transfers:</span></span>

  - <span data-ttu-id="e5ccc-169">**Включить фильтр**   файлов этот параметр включает фильтрацию файлов для глобального развертывания или для выбранного сайта.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-169">**Enable file filter**   This option enables file filtering for the global deployment or for the site that you select.</span></span>
    
    <span data-ttu-id="e5ccc-170">Если вы включите фильтр файлов, вы можете выбрать один из следующих вариантов **передачи файлов**.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-170">When you enable the file filter, you can choose one of the following options in **File transfer**:</span></span>
    
      - <span data-ttu-id="e5ccc-171">**Заблокируйте определенные типы**   файлов, на которые отфильтруются запросы на передачу файлов, указав список блокируемых расширений файлов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-171">**Block specific file types**   You specify which file transfer requests are filtered by the server by specifying a list of file extensions to block.</span></span> <span data-ttu-id="e5ccc-172">Записи в списке могут содержать все стандартные символы, но не подстановочные знаки (\*).</span><span class="sxs-lookup"><span data-stu-id="e5ccc-172">Entries in the list can contain all standard characters, but not the wildcard character (\*).</span></span> <span data-ttu-id="e5ccc-173">В клиенте Office Live Meeting 2007 функция выдач включена, но любой файл с этим расширением не удается загрузить или загрузить.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-173">In the Office Live Meeting 2007 client the handout feature is enabled, but any file with this extension cannot be uploaded or downloaded.</span></span> <span data-ttu-id="e5ccc-174">Если установить флажок **блокировать URL-адреса с расширением файла** на вкладке **Фильтр** URL-адреса, то фильтр URL-адреса использует тот же список для блокирования активных гиперссылок, которые содержат любое из этих расширений файлов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-174">If you select the **Block URLs with file extension** check box on the settings for a URL filter listed on the **URL Filter** tab, the URL filter uses this same list to block active hyperlinks that contain any of these file extensions.</span></span> <span data-ttu-id="e5ccc-175">Чтобы выбрать типы файлов, которые вы хотите заблокировать, нажмите кнопку **выбрать**, а затем в списке **выберите тип файла**добавьте расширения типов файлов в список **выбранные расширения типов файлов** .</span><span class="sxs-lookup"><span data-stu-id="e5ccc-175">To choose which file types you want to block, click **Select**, and then, in **Select File Type**, add the file type extensions to the **Selected file type extensions** list.</span></span>
    
      - <span data-ttu-id="e5ccc-176">**Блокировать весь**   сервер удаляет все мгновенные сообщения, содержащие запросы на передачу файлов, и возвращает сообщение об ошибке отправителю запроса.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-176">**Block All**   The server drops all instant messages that contain file transfer requests and returns an error message to the sender of the request.</span></span> <span data-ttu-id="e5ccc-177">Функция выдач в клиенте Office Live Meeting 2007 отключена.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-177">The handout feature in the Office Live Meeting 2007 client is disabled.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e5ccc-178">Фильтрация расширений файлов ограничена стандартными именами файлов.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-178">Filtering of file extensions is limited to standard file names.</span></span> <span data-ttu-id="e5ccc-179">Фильтрация не работает с расширениями файлов, внедренными в другие имена.</span><span class="sxs-lookup"><span data-stu-id="e5ccc-179">Filtering may not work with file extensions embedded in other names.</span></span>



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e5ccc-180">Содержание</span><span class="sxs-lookup"><span data-stu-id="e5ccc-180">In This Section</span></span>

  - [<span data-ttu-id="e5ccc-181">Изменение фильтра передачи файлов по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5ccc-181">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [<span data-ttu-id="e5ccc-182">Создание нового фильтра передачи файлов в Lync Server 2013 для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="e5ccc-182">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [<span data-ttu-id="e5ccc-183">Изменение фильтра URL-адреса по умолчанию в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5ccc-183">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)

  - [<span data-ttu-id="e5ccc-184">Создание фильтра URL-адресов в Lync Server 2013 для обработки гиперссылок в текстовых беседах</span><span class="sxs-lookup"><span data-stu-id="e5ccc-184">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5ccc-185">См. также</span><span class="sxs-lookup"><span data-stu-id="e5ccc-185">See Also</span></span>


[<span data-ttu-id="e5ccc-186">Управление параметрами обмена мгновенными сообщениями и сведениями о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5ccc-186">Managing IM and presence settings in Lync Server 2013</span></span>](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

