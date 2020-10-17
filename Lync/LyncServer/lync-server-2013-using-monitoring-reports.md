---
title: 'Lync Server 2013: использование отчетов мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae3182dd6129d9ce797739220faeef0cd97a3a92
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518816"
---
# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="66fbb-102">Использование отчетов мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66fbb-102">Using Monitoring Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66fbb-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="66fbb-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="66fbb-104">Lync Server 2013 включает набор стандартных отчетов, публикуемых службой отчетов Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66fbb-104">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="66fbb-105">Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в база данных CDR и QoE.</span><span class="sxs-lookup"><span data-stu-id="66fbb-105">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="66fbb-106">Чтобы использовать эти отчеты, необходимо установить отчеты мониторинга на компьютере, на котором запущен экземпляр SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66fbb-106">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="66fbb-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="66fbb-107">In This Section</span></span>

  - <span data-ttu-id="66fbb-108">[Использование панели мониторинга в Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)     Предоставляет администраторам краткие сведения о работоспособности и использовании системы.</span><span class="sxs-lookup"><span data-stu-id="66fbb-108">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="66fbb-109">[Отчеты об использовании системы в Lync Server 2013](lync-server-2013-system-usage-reports.md)     Предоставляет сведения об использовании системы на основе данных CDR, собранных Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66fbb-109">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="66fbb-110">[Диагностические отчеты по вызовам (на пользователя) в Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)     Предоставляет сведения о неудачных одноранговых сеансах и сеансах конференц-связи для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="66fbb-110">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="66fbb-111">[Диагностические отчеты по вызовам в Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)     Предоставляет сводную информацию и диагностические данные для неудачных одноранговых сеансов и сеансов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="66fbb-111">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="66fbb-112">[Диагностические отчеты по качеству мультимедиа в Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)     Предоставляет сведения о качестве вызовов, а также диагностические сведения и сведения об устранении неполадок для неудачных вызовов.</span><span class="sxs-lookup"><span data-stu-id="66fbb-112">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="66fbb-113">Поиск записей</span><span class="sxs-lookup"><span data-stu-id="66fbb-113">Locating Records</span></span>

<span data-ttu-id="66fbb-p102">Одновременно отчеты мониторинга отображают на экране лишь ограниченное число записей. Фактическое число отображаемых записей зависит от отчета. Чтобы просмотреть записи, которые в данный момент не отображаются на экране, вы можете использовать стандартный элемент управления для перехода вперед и назад (который присутствует на панели инструментов каждого отчета) для прокрутки страниц с данными. Вы также можете быстро перейти к первой или последней странице набора данных.</span><span class="sxs-lookup"><span data-stu-id="66fbb-p102">Monitoring Reports only show a limited number of records on the screen at any one time. The actual number of records displayed on a screen varies depending on the report. To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data. You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="66fbb-118">Кроме использования элементов управления для перехода вперед и назад, вы также можете перейти к любой странице набора данных, просто введя номер страницы в поле **Текущая страница** и нажав клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="66fbb-118">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="66fbb-p103">Кроме возможности прокрутки страниц данных, в каждом отчете имеется ограниченная возможность поиска записей. Чтобы найти записи по заданному значению, введите его в поле **Поиск** и нажмите кнопку **Найти**. В отчете начинается поиск по данным, который останавливается на первом экземпляре со значением, введенным в поле **Поиск**. Чтобы найти следующую запись, удовлетворяющую критерию поиска, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="66fbb-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="66fbb-p104">Как уже было отмечено, отчеты сервера мониторинга предоставляют только самые базовые функции поиска. Например, нельзя указать поле, в котором должно содержаться искомое значение. Механизм поиска автоматически ищет совпадающие значения в каждом поле каждой записи. Вы не можете использовать подстановочные знаки во время поиска, поэтому всегда выполняется поиск только конкретных значений. Это означает, что при поиске значения 111 будет найдено как поле со значением 111, так и поля со значениями 11100, 811, 3112, 611A5B и любыми другими значениями, содержащими 111.</span><span class="sxs-lookup"><span data-stu-id="66fbb-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="66fbb-p105">Каждый отчет настроен на отображение установленного по умолчанию набора записей. Например, по умолчанию в отчете о регистрации пользователей отображаются операции регистрации пользователей за прошлую неделю. В некоторых ситуациях это может привести к отсутствию записей в отчете. В данном случае это означает, что на прошлой неделе не регистрация пользователей не выполнялась. Если отображается сообщение "No results match the report filters" (Результаты, соответствующие фильтрам отчета, отсутствуют), попробуйте изменить значения фильтра (например, измените период времени с последней недели на последний месяц) и выполнить запрос повторно. Дополнительные сведения см. ниже в подразделе "Фильтрация данных".</span><span class="sxs-lookup"><span data-stu-id="66fbb-p105">Each report is configured to show a default set of records. For example, by default the User Registration Report shows user registration activities for the past week. In some cases, this might result in a report that returns no records. In this case, it means that no user registrations have taken place in the past week. If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query. For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="66fbb-134">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="66fbb-134">Filtering Data</span></span>

<span data-ttu-id="66fbb-p106">В некоторых ситуациях вам может потребоваться просмотреть только подмножество записей. Например, только одноранговые сеансы вместо одноранговых сеансов и сеансов конференц-связи. Аналогичным образом, в некоторых ситуациях вам может потребоваться сократить число возвращаемых записей. По умолчанию отчет может отобразить в наборе данных первую 1000 записей. Для решения таких проблем большинство отчетов содержит параметры фильтрации. Например, если вы хотите просмотреть только записи за период с 1 января 2011 года по 15 января 2011 года, можно указать 1 января 2011 года в поле **С** и 15 января 2011 года в поле **По**. Если после этого щелкнуть элемент **Просмотреть отчет**, будут возвращены только данные по операциям, выполненным с 1 января 2011 года по 15 января 2011 года.</span><span class="sxs-lookup"><span data-stu-id="66fbb-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="66fbb-p107">Доступные фильтры зависят от просматриваемого отчета. Дополнительные сведения о каждом из отчетов см. в соответствующем разделе справки.</span><span class="sxs-lookup"><span data-stu-id="66fbb-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="66fbb-144">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="66fbb-144">Exporting Data</span></span>

<span data-ttu-id="66fbb-p108">Отчеты мониторинга предоставляют по крайней мере два различных способа экспорта включенных в отчет данных. Вы можете использовать параметр **Экспорт** на панели инструментов, отображаемой в верхней части каждого отчета. Чтобы использовать данную возможность, сначала выберите требуемый формат экспорта в раскрывающемся списке **Выберите формат**. Доступны следующие форматы:</span><span class="sxs-lookup"><span data-stu-id="66fbb-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>

  - <span data-ttu-id="66fbb-149">XML-файл с данными отчета</span><span class="sxs-lookup"><span data-stu-id="66fbb-149">XML file with report data</span></span>

  - <span data-ttu-id="66fbb-150">CSV (с разделителями-запятыми)</span><span class="sxs-lookup"><span data-stu-id="66fbb-150">CSV (comma delimited)</span></span>

  - <span data-ttu-id="66fbb-151">Файл Acrobat (PDF)</span><span class="sxs-lookup"><span data-stu-id="66fbb-151">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="66fbb-152">MHTML (веб-архив)</span><span class="sxs-lookup"><span data-stu-id="66fbb-152">MHTML (web archive)</span></span>

  - <span data-ttu-id="66fbb-153">Excel</span><span class="sxs-lookup"><span data-stu-id="66fbb-153">Excel</span></span>

  - <span data-ttu-id="66fbb-154">Файл TIFF</span><span class="sxs-lookup"><span data-stu-id="66fbb-154">TIFF file</span></span>

  - <span data-ttu-id="66fbb-155">Word</span><span class="sxs-lookup"><span data-stu-id="66fbb-155">Word</span></span>

<span data-ttu-id="66fbb-p109">После выбора формата щелкните элемент **Экспорт**. В открывшемся диалоговом окне **Загрузка файла** нажмите кнопку **Сохранить**. В диалоговом окне **Сохранить как** выберите конечную папку, введите имя файла и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="66fbb-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="66fbb-p110">Если у вас установлен продукт Microsoft OneNote, вы также можете скопировать данные отчета в OneNote. Для этого щелкните правой кнопкой мыши кнопку **Просмотреть отчет** на панели инструментов. В диалоговом окне **Выберите расположение в OneNote** выберите раздел OneNote, куда вы хотите скопировать данные, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="66fbb-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

