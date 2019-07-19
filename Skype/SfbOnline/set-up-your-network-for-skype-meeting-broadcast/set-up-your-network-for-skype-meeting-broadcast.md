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
f1keywords: None
ms.custom:
- SMB
description: Узнайте о функциях трансляции собраний Skype в Skype для бизнеса Online, которая позволяет планировать, создавать и транслировать собрания или события для больших Интернет-пользователей до 10 000 участников.
ms.openlocfilehash: 443810772eeb8bf11721825b06b6a87ccb2c97c8
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792923"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Настройка сети для трансляции собраний Skype

После [включения](enable-skype-meeting-broadcast.md) трансляции собраний Skype в Skype необходимо настроить сеть. Если вы хотите хранить семинары и другие трансляции для пользователей за пределами вашей организации, выполните это действие.

Если вы не сталкивались с настройкой межсетевого экрана, рассматривайте для этого действия [партнера Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089) .

Чтобы пропустить этот шаг и добавить еще один бизнес в Федерацию, чтобы вы могли пригласить их на широковещательные показы, выполните действия, описанные в статье [Разрешение пользователей для связи с внешними пользователями Skype для бизнеса](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Шаг 1: Настройка разрешенных доменов

Чтобы настроить разрешенные домены, воспользуйтесь **одним** из описанных ниже способов.

## #

 **Способ 1: использование центра администрирования**

1. Перейдите в центр администрирования, а затем на панели навигации слева щелкните надстройки**службы &amp; ** **параметров** > и выберите **Skype для бизнеса**.

2. На странице **внешний общий доступ** в разделе **исключения домена**, выберите **все домены заблокированы, Кроме того**, введите указанные ниже домены, разделяя их запятыми (,).

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Нажмите кнопку **Сохранить**.

## #

 **Способ 2: использование Windows PowerShell**

- В **меню "Пуск**" щелкните правой кнопкой мыши **Windows PowerShell** и выберите пункт **Запуск от имени администратора**. В окне **Windows PowerShell** введите каждую строку и нажмите клавишу ВВОД.

  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Шаг 2: Добавьте домены трансляции собраний Skype, URL-адреса и адреса IP.

На втором этапе процесса настройки нужно добавить необходимые домены, а затем добавить IP-адреса и URL-адреса, необходимые для работы трансляции собраний Skype.

- **Добавьте нужные URL-адреса конечных точек Skype для бизнеса Online и IP-адреса, чтобы увидеть, какие из них являются обязательными** . [здесь](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Настройка трансляции собраний Skype в гибридных развертываниях и организациях

Если у вас есть организация Skype для бизнеса Online и локальное развертывание Lync Server 2010, Microsoft Lync Server 2013 и Skype для бизнеса Server 2015 и у них есть другие пользователи в сети и локально, необходимо выполнить другие действия по настройке, описанные в этой статье. Помимо описанных выше, чтобы предоставить локальной организации возможность общения с Skype для бизнеса Online и разрешить всем пользователям присоединиться к трансляции собраний Skype. Чтобы узнать о требованиях, ознакомьтесь с разрешениями [Настройка локального развертывания для трансляции собраний Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Статьи по теме

[Включение трансляции собрания Skype](enable-skype-meeting-broadcast.md)

[URL-адреса и диапазоны IP-адресов Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Настройка Skype для бизнеса Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



