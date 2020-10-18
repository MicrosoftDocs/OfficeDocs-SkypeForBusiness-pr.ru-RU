---
title: 'Lync Server 2013: Установка файлов агента Operations Manager'
description: 'Lync Server 2013: Установка файлов агента Operations Manager.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61bba93549e4831b65657a1fe80c918bbcb45572
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573785"
---
# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Установка файлов агента Operations Manager в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

Чтобы установить на компьютер файлы агента Operations Manager, выполните следующие действия.

1.  В установочном носителе System Center дважды щелкните программу **SetupOM.exe**.

2.  В окне установки System Center Operations Manager выберите **Установить агент Operations Manager**.

3.  На странице **приветствия** мастера установки System Center нажмите кнопку **Далее**.

4.  На странице указания **папки назначения** выберите папку, в которую должны устанавливаться файлы агента Operations Manager и нажмите кнопку **Далее**.

5.  На странице **Конфигурация группы управления** выберите **Указать сведения о группе управления** и нажмите кнопку **Далее**.

6.  На странице **Конфигурация группы управления** в поле **Имя группы управления** введите имя группы управления Operations Manager, а в поле **Сервер управления** введите имя узла сервера Operations Manager (например, atl-scom-001). Если номер порта, используемый Operations Manager, был изменен, то в поле "Порт сервера управления" укажите этот новый номер. Если номер порта не изменялся, то оставьте значение по умолчанию 5723 и нажмите кнопку **Далее**.

7.  На странице **Учетная запись действий агента** выберите **Local System** и нажмите кнопку **Далее**.

8.  На странице **Центр обновления Майкрософт** выберите **Не использовать Центр обновления Майкрософт** и нажмите кнопку **Далее**.

9.  На странице **Все готово для установки** нажмите кнопку **Установить**.

10. На странице **Завершение работы мастера установки System Center Operations Manager** нажмите кнопку **Готово**.

11. Нажмите кнопку **Выход**.

Если вы используете System Center 2007 R2, то можно проверить, создан ли агент, нажав кнопку **Пуск** и последовательно выбрав пункты **Программы**, **System Center Operations Manager 2007 R2** и **Оболочка Operations Manager**. В командной консоли Operations Manager введите следующую команду Windows PowerShell и нажмите клавишу ВВОД:

    Get-Agent 

На экране должен появиться список всех агентов Operations Manager.

Если вы используете System Center 2012, то выполните в оболочке Operations 2012 Manager Shell следующую команду:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

