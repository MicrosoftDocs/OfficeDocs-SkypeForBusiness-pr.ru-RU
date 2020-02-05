---
title: Процесс развертывания приложения для объявления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Процесс развертывания и инструкции для приложения объявления в голосовой связи Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 89f01ed4c9488aa74b07bfae41f3bf27032b552e
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767402"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="f8399-103">Процесс развертывания приложения для объявления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f8399-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="f8399-104">Процесс развертывания и инструкции для приложения объявления в голосовой связи Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f8399-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f8399-105">Приложение извещения — это функция голосовой связи, позволяющая настроить действия, которые необходимо выполнить для звонков на неназначенные расширения (расширения, которые являются допустимыми для вашей организации, но не назначены для человека или телефона).</span><span class="sxs-lookup"><span data-stu-id="f8399-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="f8399-106">Например, можно настроить эту функцию таким образом, чтобы при выполнении вызовов на неприсвоенные номера воспроизводилось сообщение и/или эти вызовы передавались на другое назначение.</span><span class="sxs-lookup"><span data-stu-id="f8399-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="f8399-107">Приложение извещения устанавливается как функция приложения группы ответа на сервере переднего плана или стандартном сервере Standard Edition при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f8399-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f8399-108">Для настройки оповещений следует загрузить аудиофайлы или настроить преобразование текста в речь и сконфигурировать таблицу неприсвоенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f8399-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="f8399-109">В этом разделе приводятся общие сведения о том, какие действия выполняются при развертывании приложения объявлений.</span><span class="sxs-lookup"><span data-stu-id="f8399-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="f8399-110">Перед настройкой объявлений необходимо развернуть корпоративный голос.</span><span class="sxs-lookup"><span data-stu-id="f8399-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="f8399-111">Компоненты, необходимые для приложения извещения, устанавливаются и включаются при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f8399-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="f8399-112">**Процесс развертывания объявлений**</span><span class="sxs-lookup"><span data-stu-id="f8399-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="f8399-113">**Этап**</span><span class="sxs-lookup"><span data-stu-id="f8399-113">**Phase**</span></span>|<span data-ttu-id="f8399-114">**Шаги**</span><span class="sxs-lookup"><span data-stu-id="f8399-114">**Steps**</span></span>|<span data-ttu-id="f8399-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="f8399-115">**Roles**</span></span>|<span data-ttu-id="f8399-116">**Документация по развертыванию**</span><span class="sxs-lookup"><span data-stu-id="f8399-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8399-117">Настройка параметров объявлений</span><span class="sxs-lookup"><span data-stu-id="f8399-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="f8399-118">Создайте объявление, записав и отправив звуковые файлы или воспользовавшись преобразованием текста в речь.</span><span class="sxs-lookup"><span data-stu-id="f8399-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="f8399-119">Настройте диапазоны неназначенных номеров в таблице неназначенных номеров и свяжите их с соответствующим объявлением.</span><span class="sxs-lookup"><span data-stu-id="f8399-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="f8399-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f8399-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="f8399-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8399-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="f8399-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8399-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="f8399-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8399-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="f8399-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="f8399-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="f8399-125">Создание и удаление объявлений в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f8399-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="f8399-126">Создание и изменение неназначенного диапазона номеров в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f8399-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="f8399-127">Проверка развертывания объявления</span><span class="sxs-lookup"><span data-stu-id="f8399-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="f8399-128">Выполните тестовое прослушивание объявлений, чтобы убедиться в их правильной работе.</span><span class="sxs-lookup"><span data-stu-id="f8399-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="f8399-129">Необязательно Проверка развертывания объявления в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f8399-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

