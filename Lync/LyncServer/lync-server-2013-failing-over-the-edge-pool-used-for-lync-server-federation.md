---
title: 'Lync Server 2013: отработка отказа для пограничного пула, используемого для федерации Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f144def3d3a8df9cc63221342a85666eb3c28913
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Отработка отказа для пограничного пула, используемого для федерации Lync Server в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-17_

Если пул пограничного пула, на котором настроена сервер Lync Server Federation, не работает, необходимо изменить Федерацию для использования другого пула Edge для работы Федерации.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Сбой в пуле EDGE, используемом для интеграции с Lync Server

1.  На сервере переднего плана откройте окно Построитель топологии. Разверните узел **Edge**Pools, а затем щелкните правой кнопкой мыши граничный сервер пограничного сервера или пул пограничного сервера, настроенный на данный момент для Федерации. Нажмите кнопку **изменить свойства**.

2.  В диалоговом окне **изменение свойств** в разделе **Общие**снимите флажок **включить федерацию для этого пограничного пула (порт 5061)**. Нажмите кнопку **ОК**.

3.  Разверните узел **Edge**Pools, а затем щелкните правой кнопкой мыши граничный сервер пограничного сервера или пул пограничного сервера, который вы хотите использовать для Федерации. Нажмите кнопку **изменить свойства**.

4.  В диалоговом окне **изменение свойств** в разделе **Общие**установите флажок **включить федерацию для этого пограничного пула (порт 5061)**. Нажмите кнопку **ОК**.

5.  Нажмите кнопку **действие**, выберите пункт **топология**, нажмите кнопку **опубликовать**. При появлении запроса на **публикацию топологии**нажмите кнопку **Далее**. Завершив публикацию, нажмите кнопку **Готово**.

6.  На пограничном сервере откройте мастер развертывания Lync Server. Щелкните **Установка или обновление операционной системы Lync Server**, а затем нажмите кнопку **Настройка или удалите компоненты Lync Server**. Нажмите кнопку **выполнить еще раз**.

7.  В разделе Настройка серверных компонентов Lync нажмите кнопку **Далее**. На экране сводки будут показаны действия по мере их выполнения. После завершения развертывания щелкните **Просмотреть журнал** , чтобы просмотреть доступные файлы журнала. Нажмите кнопку **Готово** , чтобы завершить развертывание.
    
    Если сайт, содержащий неисправный пул, содержит серверы переднего плана, которые еще не запущены, для использования пула EDGE на удаленном сайте, который еще не работает, необходимо обновить службу веб-конференций и службу Конференции/V на этих интерфейсных пулах. Дополнительные сведения можно найти [в разделе Изменение пула EDGE, связанного с пулом переднего плана в Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>См. также


[Отработка отказа для пограничного пула, используемого для федерации XMPP в Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Отработка отказа для пограничного пула, используемого для федерации Lync Server или федерации XMPP в Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Аварийное восстановление пограничного сервера в Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

