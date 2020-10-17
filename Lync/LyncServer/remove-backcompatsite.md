---
title: Удаление BackCompatSite
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba13ec0bf942298748b18ac1c94418275c728949
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500096"
---
# <a name="remove-backcompatsite"></a>Удаление BackCompatSite

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

После отключения всех пулов и удаления всех пограничных серверов запустите мастер объединения построителя топологий, чтобы удалить узел **BackCompatSite**.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>Удаление сайта BackCompat из построителя топологий

1.  Откройте существующую среду в окне построителя топологий.

2.  В меню **Действие** выберите **Объединить топологию 2007 R2**.

3.  Нажмите кнопку **Далее**, чтобы продолжить.

4.  На странице **указание устаревшей пограничной** страницы убедитесь, что список пограничных серверов пуст. Если этот список не пуст, нажмите кнопку **Удалить**, чтобы удалить все унаследованные пограничные серверы, а затем нажмите кнопку **Далее**.
    
    ![Мастер создания топологии слиянием, задать страницу настройки пограничного сервера](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Мастер создания топологии слиянием, задать страницу настройки пограничного сервера")  

5.  На странице **Определение значения внутреннего порта SIP** нажмите кнопку **Далее**.

6.  На странице **Сводка** нажмите кнопку **Далее** , чтобы начать объединение топологий для удаления устаревшего сайта.

7.  Убедитесь, что столбец **Состояние** содержит значение **Успешно**, а затем нажмите кнопку **Готово**, чтобы закрыть мастер.

8.  В левой части построителя топологий разверните BackCompatSite и убедитесь в отсутствии серверов в списке.

9.  Щелкните правой кнопкой мыши **BackCompatSite** и выберите команду **Удалить**.

10. В **Построителе топологий** выберите узел верхнего уровня **Lync Server**.

11. В меню **Действие** выберите пункт **Опубликовать топологию**, затем нажмите кнопку **Далее**.

12. По завершении работы **мастера публикации** нажмите кнопку **Готово**, чтобы закрыть мастер.

</div>

</div>

<span> </span>

</div>

</div>

</div>

