---
title: 'Lync Server 2013: указание хранения данных CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32eee413b25da3231d5633e89571bbc08deb1f38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a>Определение хранения данных CDR в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

По умолчанию данные регистрации вызовов (CDR) удаляются по прошествии 60 дней. Можно использовать параметры на странице **Регистрация вызовов**, чтобы задать хранение данных в течение большего или меньшего времени. Если отключить CDR, то данные, которые были записаны до включения CDR, также будут удаляться.

<div>


> [!NOTE]  
> Необходимо настроить CDR и качество взаимодействия (QoE) для хранения данных в течении одинакового числа дней. Каждый звонок в отчетах CDR, доступных на веб-странице отчетов сервера мониторинга, включает сведения CDR и качества взаимодействия. Если время для удаления данных CDR и качества взаимодействия отличается, некоторые звонки могут содержать только данные CDR, а другие могут содержать только данные качества взаимодействия.



</div>

Для настройки параметров очистки данных CDR используется следующая процедура.

<div>

## <a name="to-specify-retention-of-cdr-data"></a>Настройка хранения данных CDR

1.  Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**.

4.  На странице **Регистрация вызовов** в таблице щелкните необходимый сайт, щелкните **Правка**, а затем — **Показать подробности**.

5.  Чтобы включить удаление, выберите параметр **Enable Purging of CDRs** (Включить очистку CDR).

6.  В параметре **Keep call detail recordings CDRs for maximum duration (days):** (Сохранять CDR не более (дней)) выберите максимальное число дней, в течение которых должны храниться данные регистрации вызовов.

7.  В параметре **Хранить сведения отчетов об ошибках максимум в течение (дней):** выберите максимальное число дней, в течение которых должны храниться данные отчетов об ошибках.

8.  Щелкните **Исполнить**.

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Указание хранения CDR с помощью командлетов Windows PowerShell

Вы можете создать параметры хранения CDR с помощью Windows PowerShell и командлета Set-Кскдрконфигуратион. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a>Задание параметров хранения CDR для конкретного расположения

  - Эта команда позволяет очищать данные CDR для сайта Redmond и настраивает сайт для обслуживания данных CDR и данных отчетов об ошибках в течение 20 дней.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a>Задание параметров хранения CDR для нескольких расположений

  - Эта команда настраивает параметры хранения CDR для всех параметров конфигурации CDR, используемых в организации.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

</div>

<div>

## <a name="see-also"></a>См. также


[Запись сведений о звонке (CDR) в Lync Server 2013](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

