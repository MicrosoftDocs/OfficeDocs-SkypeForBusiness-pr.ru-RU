---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Подключение пилотного пула к старым пограничным серверам

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

После развертывания Lync Server 2013 маршрут Федерации для этого сайта не настроен. Чтобы использовать федеративный маршрут, используемый Office Communications Server 2007 R2, Lync Server 2013 должен быть настроен для использования этого маршрута.

Чтобы разрешить сайту Lync Server 2013 использовать директор и пограничный сервер BackCompatSite, используйте построитель топологий для связи устаревшего пограничного пула.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Сопоставление старого пограничного пула с помощью построителя топологии

1.  Откройте пилотную топологию пула в построителе топологии.

2.  Выберите сайт Lync Server 2013.

3.  В меню **Действие** щелкните **Изменить свойства**.

4.  В разделе **назначение федеративного маршрута сайта**выберите **включить федерацию SIP**, а затем выберите Office Communications Server 2007 R2 или пограничный сервер Office Communications Server 2007 R2, если в списке нет директоров.
    
    ![Диалоговое окно "изменение свойств", страница "маршрут Федерации"](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "маршрут Федерации"")  

5.  Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.

6.  В построителе топологий разверните узел Lync Server 2013 и перейдите к пулам **переднего плана** **сервера Standard Edition** или Enterprise Edition, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.

7.  В разделе **Связи** установите флажок **Сопоставить пограничный пул (для компонентов мультимедиа)**.

8.  Выберите из списка интерфейс пограничного сервера для BackCompatSite.
    
    ![Диалоговое окно "изменение свойств", страница "Общие"](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "Общие"")  

9.  Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.

10. В **построителе топологий** выберите самый верхний узел, **Lync Server**.

11. В меню **Action** (Действие) выберите команду **Publish Topology** (Опубликовать топологию) и нажмите кнопку **Далее**.

12. Когда **мастер публикации** завершит работу, нажмите кнопку **Готово**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

