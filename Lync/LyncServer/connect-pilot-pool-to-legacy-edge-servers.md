---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9213dbf5d75b80ccbfc67d03cfb3c02ef87145
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Подключение пилотного пула к старым пограничным серверам

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-29_

После развертывания Lync Server 2013 необходимо настроить маршрут Федерации для сайта. Чтобы использовать федеративный маршрут, используемый Lync Server 2010, необходимо настроить Lync Server 2013 для использования этого маршрута.

Чтобы разрешить сайту Lync Server 2013 использовать директор и пограничный сервер развертывания Lync Server 2010, используйте построитель топологий для связи устаревшего пограничного пула.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Связь устаревшего пограничного пула с помощью построителя топологий

1.  Откройте **построитель топологий**.

2.  Выберите свой сайт, который находится сразу под узлом **Lync Server**.

3.  В меню **Actions** (Действия) выберите команду **Изменить свойства**.

4.  В левой области выберите **Федеративный маршрут**.

5.  В разделе **назначение федеративного маршрута сайта**выберите **включить федерацию SIP**, а затем выберите режиссер Lync Server 2010 или пограничный сервер Lync Server 2010, если в списке нет директоров.
    
    ![Страница "изменить свойства", "маршрут Федерации"](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Страница "изменить свойства", "маршрут Федерации"")  

6.  Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.

7.  В построителе топологий разверните узел Lync Server 2013 и перейдите к пулам **переднего плана** **сервера Standard Edition** или Enterprise Edition, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.

8.  В разделе **Associations** (Связи) установите флажок **Associate Edge pool (for media components)** (Связать пограничный пул (для компонентов медиа)).

9.  Выберите в списке устаревший пограничный сервер.
    
    ![Диалоговое окно "изменение свойств" с выбором прежнего пограничного края](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Диалоговое окно "изменение свойств" с выбором прежнего пограничного края")  

10. Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.

11. В **построителе топологий** выберите самый верхний узел, **Lync Server**.

12. В меню **Action** (Действие) выберите команду **Publish Topology** (Опубликовать топологию) и нажмите кнопку **Далее**.

13. Когда **мастер публикации** завершит работу, нажмите кнопку **Готово**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

