---
title: Перевод совмещенного сервера-посредника на автономный сервер-посредник (необязательно)
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce0228edacba502161c4d44a6a94b38cede6655
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Перевод совмещенного сервера-посредника на автономный сервер-посредник (необязательно)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Используйте следующую процедуру для переноса сервера-посредника, совместно размещаемого на сервере Standard Edition или в пуле переднего плана, на автономный сервер-посредник для развертывания на одном сайте.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Перенос совместно размещаемого сервера-посредника на автономный сервер-посредник

1.  Откройте существующую топологию в окне построителя топологий.

2.  В левой области перейдите к узлу **Пулы-посредники**.

3.  Щелкните правой кнопкой **Пулы-посредники** и выберите команду **Создать сервер-посредник**.

4.  On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.

5.  Выберите пул серверов переднего плана следующего прыжка, в который сервер-посредник будут направлять входящие звонки, а затем нажмите **Далее**.

6.  Выберите пограничный пул для использования этим сервером-посредником и нажмите **Далее**.

7.  On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.

8.  Нажмите кнопку **Готово**, чтобы закрыть мастер **Определение нового пула-посредника**.

9.  В **построителе топологий**выберите верхний узел **Lync Server 2013**.

10. В области **Действия** выберите команду **Опубликовать топологию** и завершите работу мастера.

11. Выполните действия, описанные в статье [Установка файлов для сервера-посредника в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) , в документации по развертыванию, чтобы установить файлы на новый сервер-посредник.

12. После установки файлов на сервер-посредник вернитесь к построителю топологий и в левой области перейдите к пулу.

13. Щелкните пул правой кнопкой и выберите команду **Изменить свойства**.

14. В разделе **Сервер-посредник** снимите флажок **Сервер-посредник с совмещенным расположением включен** и нажмите кнопку **ОК**.

15. В **построителе топологий**выберите верхний узел **Lync Server 2013**.

16. В меню **Макрокоманда** выберите **Публикация топологии** и выполните мастер.

</div>

</div>

<span> </span>

</div>

</div>

</div>

