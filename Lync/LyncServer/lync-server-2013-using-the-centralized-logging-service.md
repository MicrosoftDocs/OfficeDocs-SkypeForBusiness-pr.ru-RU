---
title: 'Lync Server 2013: использование централизованной службы ведения журналов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Использование централизованной службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Служба централизованного ведения журналов — это новая функция в Lync Server 2013. Это улучшенная замена средств **окслогжер** и **окстрацер** , которые были указаны в предыдущих выпусках. С помощью централизованной службы ведения журнала можно выполнять следующие задачи:

  - Начните вести вход на одном или нескольких компьютерах и пулах из одного места и из одной команды.

  - Прекращение ведения журнала на одном или нескольких компьютерах и пулах из одного места и команды.

  - Поиск в журналах на одном или нескольких компьютерах и пулах для одного места и команды. Вы можете настроить команду поиска так, чтобы она возвращала все агрегированные журналы, которые были собраны и сохранены на всех компьютерах, или вернуть сокращенные результаты, которые захватывают определенные данные.

  - Настройте сеансы ведения журналов следующим образом:
    
      - Define a **Scenario**, or use a default scenario. *Сценарий* централизованной службы ведения журнала состоит из области охвата (Global или site), имени сценария для идентификации назначения сценария и одного или нескольких поставщиков. Вы можете запускать два сценария в любой момент на компьютере.
    
      - Используйте существующего *поставщика* или создайте нового. *Поставщик* определяет, что собирает сеанс ведения журналов, каков уровень детализации, какие компоненты отслеживаются и какие флаги применяются.
        
        <div>
        

        > [!TIP]  
        > If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG). Эти элементы определяются в поставщике (переменной Windows PowerShell) и передаются команде централизованной службы ведения журнала.

        
        </div>
    
      - Настройте компьютеры и пулы, из которых вы хотите собирать журналы.
    
      - Определите область для сеанса ведения журнала на **сайте** параметров (ведение журнала для всех компьютеров только на этом сайте) или **Global** (выполните ведение журнала на всех компьютерах в развертывании).

Централизованная служба ведения журнала является чрезвычайно мощной и может значительно отвечать за проблемы, возникающие при устранении неполадок — крупный или малый. После анализа корневой причины проблем с производительностью централизованная служба ведения журналов может быть важным инструментом для любого администратора. Все примеры отображаются в командной консоли Lync Server Management Shell. Для централизованной службы ведения журналов под названием **клсконтроллер. exe**есть компонент командной строки. Справка предоставляется для средства командной строки с помощью самого инструмента. Тем не менее, в командной строке можно выполнить ограниченный набор функций. С помощью командной консоли Lync Server вы можете получить доступ к гораздо большему и более настраиваемому набору функций. При использовании централизованной службы ведения журналов следует использовать командную консоль Lync Server в качестве первой и самой основной функции.

В этом разделе объясняется, как использовать централизованную службу ведения журналов и примеры того, как пользоваться ее многими функциями.

<div>

## <a name="in-this-section"></a>Содержание

  - [Общие сведения об централизованной службе ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Управление централизованными параметрами конфигурации службы ведения журналов в Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Общие сведения о централизованных параметрах конфигурации службы ведения журналов в Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Использование команды Start для централизованной службы ведения журналов для захвата журналов в Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Использование функции "остановить" для централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Использование функции поиска в журналах захвата, созданных службой централизованного ведения журналов в Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Чтение журналов захвата из службы централизованного ведения журналов в Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

