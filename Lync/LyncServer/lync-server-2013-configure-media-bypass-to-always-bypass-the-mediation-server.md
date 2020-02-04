---
title: 'Lync Server 2013: Настройка обхода мультимедийных файлов для постоянного обобхода сервера обновлений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0023fba32b24243dc4bf2a12659700ace6dea91a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configure media bypass in Lync Server 2013 to always bypass the Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-25_

<div>


> [!NOTE]  
> В этой статье предполагается, что вы уже настроили мультимедиа для всех магистральных подключений к однорангового канала (коммутируемая телефонная сеть (PSTN), IP-УАТС или контроллер границ сеанса (SBC) в поставщике услуг телефонной связи через Интернет (ИТСП)) для определенного сайт или служба, для которых требуется, чтобы мультимедиа обходило сервер-посредник.<BR>Вы не можете настроить мультимедиа так, чтобы он всегда обходился на сервере, а также включать управление допуском звонков. Эти параметры несовместимы и, следовательно, являются взаимоисключающими параметрами в пользовательском интерфейсе панели управления Lync Server.



</div>

Кроме включения функции обхода мультимедиа для отдельных магистральных подключений, связанных с одноранговым сервером, необходимо также настроить общие параметры для обхода мультимедиа. Если вы используете действия, описанные в этом разделе, чтобы настроить общие параметры для обхода мультимедиа, предполагается, что у вас есть хорошее соединение между конечными точками Lync и любым одноранговым узлом, для которого вы настроили обходные носители на магистральном подключении.

Если у вас нет хорошей связи между конечными точками Lync Server и всеми одноранговыми узлами на сервере-посреднике, для которого соответствующие магистральные подключения включены для обхода мультимедиа, необходимо настроить глобальные параметры обхода мультимедиа, чтобы использовать сведения о сайте и регионе при используется обход мультимедиа. Это позволяет более подробно управлять тем, когда мультимедиа обходит сервер исправлений. Для этого выполните действия, описанные в разделе [Настройка обхода мультимедиа в глобальных параметрах Lync server 2013, чтобы использовать сведения о сайте и регионе](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) и [связать подсеть с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) .

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Чтобы включить глобальный постоянный обход сервера-посредника, выполните следующие действия.

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети**.

3.  Дважды щелкните конфигурацию **Глобальная** в данном списке.

4.  На странице **Изменение глобального параметра** установите флажок **Включить обхода сервера-посредника**.

5.  Щелкните **Всегда обходить**.

6.  Нажмите **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка обхода сервера-посредника в Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Глобальные параметры обхода мультимедиа в Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Сервер-посредник и обход сервера посредника в Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Планирование обхода серверов-посредников в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

