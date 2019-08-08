---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b28002e8bb060e9ac966121a419d8475b4828258
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Настройка доверенных серверов приложений

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-04_

В смешанной среде при создании нового доверенного сервера приложений после объединения старой топологии сервера Office Communications с Lync Server 2013 и определения нового доверенного сервера приложений с помощью Topology Builder необходимо настроить пул следующего прыжка как Пул Lync Server 2013. В Объединенной среде в раскрывающемся списке отображаются устаревшая группа Office Communications Server и пул Lync Server 2013. Выбор устаревшего пула *не* поддерживается.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Выбор пункта Lync Server 2013 в качестве следующего прыжка при создании надежного сервера приложений

1.  Откройте существующую топологию в построителе топологии.

2.  В левой области щелкните правой кнопкой мыши **Доверенные серверы приложений** и выберите команду **создать доверенный пул приложений**.

3.  Введите **полное доменное имя пула** для доверенного пула приложений и укажите, будет ли это развертывание одним сервером или с несколькими серверами.

4.  Нажмите кнопку **Далее**.

5.  На странице **Выбор следующего прыжка** в списке выберите пул внешних интерфейсов Lync Server 2013.
    
    ![Диалоговое окно определения нового доверенного пула приложений] (images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Диалоговое окно определения нового доверенного пула приложений")  

6.  Нажмите **Готово**.

7.  Выберите верхний узел **Lync Server** и на панели **действия** нажмите кнопку **опубликовать**.

8.  Убедитесь, что **доверенный пул приложений** успешно создан и связан с правильным пулом переднего плана.

</div>

</div>

<span> </span>

</div>

</div>

</div>

