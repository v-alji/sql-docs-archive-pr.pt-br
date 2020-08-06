---
title: Personalizar o comportamento de separadores de palavras com um dicionário personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: a8e278d1-aeaa-48f1-a0c6-5de232c983e4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9fb02a47da20134925d9b2486ea0c08091af4aa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680882"
---
# <a name="customize-the-behavior-of-word-breakers-with-a-custom-dictionary"></a><span data-ttu-id="af476-102">Personalizar o comportamento de separadores de palavras com um dicionário personalizado</span><span class="sxs-lookup"><span data-stu-id="af476-102">Customize the Behavior of Word Breakers with a Custom Dictionary</span></span>
  <span data-ttu-id="af476-103">Você pode personalizar o comportamento do separador de palavras por um idioma específico criando um arquivo de dicionário personalizado específico do idioma.</span><span class="sxs-lookup"><span data-stu-id="af476-103">You can customize the behavior of the word breaker for a particular language by creating a language-specific custom dictionary file.</span></span> <span data-ttu-id="af476-104">Por exemplo, você pode impedir que o separador de palavras quebre certas condições ou padrões.</span><span class="sxs-lookup"><span data-stu-id="af476-104">For example, you can prevent the word breaker from breaking certain terms or patterns.</span></span>  
  
 <span data-ttu-id="af476-105">Para obter mais informações, consulte o seguinte artigo do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="af476-105">For more information, see the following SharePoint article:</span></span>  
  
 [<span data-ttu-id="af476-106">Crie um dicionário personalizado (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="af476-106">Create a custom dictionary (SharePoint Server 2010)</span></span>](https://go.microsoft.com/fwlink/?LinkId=215011)  
  
 <span data-ttu-id="af476-107">Para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], coloque arquivos de dicionário personalizados na seguinte pasta:</span><span class="sxs-lookup"><span data-stu-id="af476-107">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], place custom dictionary files in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\<instance name>\MSSQL\Binn`  
  
 <span data-ttu-id="af476-108">Depois de criar ou alterar arquivos de dicionário personalizados, reinicie o Lançador de Daemon de texto completo SQL com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="af476-108">After creating or changing custom dictionary files, restart the SQL Full-text Daemon Launcher with the following command:</span></span>  
  
 `exec sp_fulltext_service 'restart_all_fdhosts'`  
  
  
