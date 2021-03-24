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
description: Узнайте о функции трансляции собраний Skype в Skype для бизнеса Online, которая позволяет планировать, создавать и транслировать собрания или события крупной онлайн-аудитории до 10 000 участников.
ms.openlocfilehash: 513b6f8d677550557293855389eff29dc61c21c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106515"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Настройка сети для трансляции собраний Skype

После того [как вы введете](enable-skype-meeting-broadcast.md) трансляцию собрания Skype, необходимо настроить сеть. Это необходимо, если вы хотите проводить вебинары и другие трансляции для людей за пределами вашей компании.

> [!IMPORTANT]
> Skype для бизнеса Online больше не будет работать 31 июля 2021 г., после чего доступ к службе закончится. Мы рекомендуем клиентам начать обновление до Microsoft Teams, основного клиента для связи и командной работы в Microsoft 365.

Если у вас нет опыта в настройке брандмауэра, вы можете нанять партнера Майкрософт, который сделает это за вас. [](https://go.microsoft.com/fwlink/?linkid=391089)

Чтобы пропустить этот шаг и добавить в вашу федерацию еще одну компания, чтобы пригласить их в трансляцию, выполните действия, которые необходимо предпринять, чтобы разрешить пользователям связываться с внешними пользователями [Skype для бизнеса.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>Шаг 1. Настройка разрешенных доменов

Чтобы **настроить разрешенные** домены, воспользуйтесь одним из следующих способов:

## #

 **Способ 1. Использование Центра администрирования**

1. Перейдите в Центр администрирования, а затем в области слева щелкните надстройки **"Параметры** служб", а затем выберите Skype для  >  **&amp;** **бизнеса.**

2. На странице **внешнего общего** доступа в разделе **"Исключения** для домена" выберите все домены, кроме заблокированных, и введите следующие домены, разделенные запятой (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Нажмите кнопку **Сохранить**.

## #

 **Способ 2. Используйте Windows PowerShell**

- В меню **"Пуск"** щелкните правой кнопкой **мыши** Windows PowerShell выберите "Запуск **от администратора".** В **окне Windows PowerShell** введите каждую строку и нажмите ввод.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Шаг 2. Добавление доменов, URL-адресов и IP-адресов для трансляции собраний Skype

Вторым этапом настройки является добавление необходимых доменов, а затем добавление IP-адресов и URL-адресов, необходимых для работы трансляции собраний Skype.

- **Добавьте необходимые URL-адреса** и IP-адреса конечных точек Skype для бизнеса Online, чтобы увидеть, какие из них здесь [необходимы.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Настройка трансляции собраний Skype в гибридных развертываниях и организациях

Если у вас есть организация Skype для бизнеса Online и локальное развертывание Lync Server 2010, Microsoft Lync Server 2013 и Skype для бизнеса Server 2015, а пользователи находятся как в сети, так и локально, вам потребуется настроить дополнительные действия, помимо перечисленных выше, чтобы разрешить локальной организации общаться со Skype для бизнеса Online и разрешить всем пользователям присоединяться к трансляции собраний Skype. Чтобы узнать, какие это требования, см. в настройках локального развертывания для [трансляции собраний Skype.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)

## <a name="related-topics"></a>Статьи по теме

[Включение трансляции собрания Skype](enable-skype-meeting-broadcast.md)

[URL-адреса и диапазоны IP-адресов для Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)