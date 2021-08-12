---
title: Настройка сети для трансляции собраний Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Узнайте о функции Skype трансляции собраний в Skype для бизнеса Online, которая позволяет планировать, создавать и транслировать собрания или события крупной онлайн-аудитории до 10 000 участников.
ms.openlocfilehash: 068ff156badaff9231f6e477e2f41668ea8f99fd26531f2a08155c4ee4763c05
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308030"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Настройка сети для трансляции собраний Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

После того [как Skype трансляцию](enable-skype-meeting-broadcast.md) Skype собрания, необходимо настроить сеть. Сделайте это, если вы хотите проводить вебинары и другие трансляции для людей за пределами вашей компании.

> [!IMPORTANT]
> Skype для бизнеса 31 июля 2021 г. заканчивается доступ к службе Online. Мы рекомендуем клиентам начать обновление до Microsoft Teams , основного клиента для связи и командной работы в Microsoft 365.

Если у вас нет опыта настройки брандмауэра, [](https://go.microsoft.com/fwlink/?linkid=391089) вы можете нанять партнера Майкрософт, который сделает это за вас.

Чтобы пропустить этот шаг и вместо этого добавить в свою федерацию еще одну компания, чтобы пригласить их в трансляцию, выполните действия, которые можно сделать в области Разрешить пользователям связываться с внешними Skype для бизнеса [пользователями.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>Шаг 1. Настройка разрешенных доменов

Чтобы **настроить разрешенные** домены, используйте один из следующих способов:

### <a name="method-1-use-the-admin-center"></a>Способ 1. Использование Центра администрирования

1. Перейдите в Центр администрирования, а затем в области слева щелкните надстройки **Параметры**  >  **&amp; services** и выберите Skype для бизнеса .

2. На странице **Внешний общий** доступ в разделе Исключения для домена **выберите** Все домены заблокированы, кроме и введите следующие домены, разделяя их запятой (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Нажмите кнопку **Сохранить**.

### <a name="method-2-use-windows-powershell"></a>Способ 2. Используйте Windows PowerShell

- В меню **"Пуск"** щелкните правой **кнопкой** мыши Windows PowerShell выберите пункт **Запуск от администратора**. В **окне** Windows PowerShell введите каждую строку и нажмите ввод.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Шаг 2. Добавление Skype доменов, URL-адресов и IP-адресов Skype трансляции собраний

Второй этап настройки — добавление необходимых доменов, а затем добавление IP-адресов и URL-адресов, необходимых для Skype трансляции собрания.

- **Добавьте необходимые URL Skype для бизнеса и IP-адреса** конечных точек Online, чтобы увидеть, какие из них здесь [необходимы.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Настройка Skype собраний в гибридных развертываниях и организациях

Если у вас есть организация Skype для бизнеса Online и локальное развертывание Lync Server 2010, Microsoft Lync Server 2013 и Skype для бизнеса Server 2015, а пользователи находятся как в сети, так и локально, вам потребуется настроить дополнительные действия, помимо перечисленных выше, чтобы разрешить локальной организации общаться с Skype для бизнеса Online и разрешить всем пользователям присоединиться к трансляции собрания Skype. Чтобы узнать, каковы эти требования, см. настройка локального развертывания для [Skype трансляции собраний.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)

## <a name="related-topics"></a>Статьи по теме

[Включение трансляции собрания Skype](enable-skype-meeting-broadcast.md)

[URL-адреса и диапазоны IP-адресов для Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
