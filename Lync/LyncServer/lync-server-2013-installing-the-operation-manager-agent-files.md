---
title: 'Lync Server 2013: Установка файлов агента Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8675e6c75c288e6594e45ecdcc2f65497a047a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Установка файлов агента Operations Manager в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

Чтобы установить файлы агента Operations Manager на компьютере, выполните указанные ниже действия.

1.  На установочном носителе System Center дважды щелкните **сетупом. exe**.

2.  В программе System Center Operation Manager нажмите кнопку **установить агент Operations Manager**.

3.  В мастере настройки System Center на странице **Добро пожаловать в мастер настройки System Center Operations Manager** нажмите кнопку **Далее**.

4.  На странице **Конечная папка** выберите папку, в которую будут установлены файлы агента Operations Manager, и нажмите кнопку **Далее**.

5.  На странице **Конфигурация группы управления** выберите **задать сведения о группе управления**, а затем нажмите кнопку **Далее**.

6.  На странице **Конфигурация группы управления** введите имя группы управления Operations Manager в поле **имя группы управления** , а затем введите имя узла сервера Operations Manager (например, ATL-SCOM-001) в ** Поле сервер управления** . Если вы изменили номер порта, используемый Operations Manager, введите новый номер порта в поле Порт сервера управления. В противном случае оставьте значение по умолчанию для порта 5723 и нажмите кнопку **Далее**.

7.  На странице **учетной записи действия агента** выберите пункт **Локальная система**и нажмите кнопку **Далее**.

8.  На странице **центра обновления Майкрософт** выберите вариант **я не хочу использовать Microsoft Update**и нажмите кнопку **Далее**.

9.  На странице " **Готово для установки** " нажмите кнопку " **установить**".

10. На странице **Завершение работы мастера установки System Center Operations Manager** нажмите кнопку **Готово**.

11. Нажмите кнопку **Выход**.

Если вы используете System Center 2007 R2, вы можете проверить, создан ли агент, нажав кнопку **Пуск**, последовательно выбрав пункты **все программы**, **System Center Operations Manager 2007 R2**и выбрав команду **Shell Operations Manager**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:

    Get-Agent 

На экран будет отображен список всех агентов Operations Manager.

Если вы используете System Center 2012, выполните эту команду из оболочки диспетчера Operations 2012:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

