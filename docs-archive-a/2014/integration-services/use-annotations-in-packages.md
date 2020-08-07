---
title: Usar anotações em pacotes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- self-documenting packages
- adding annotations
- annotations [Integration Services]
ms.assetid: 48c8ed9a-b10d-490c-9ba7-4b77aa44e3dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 27c7df6afd894ea9730027da1d54786ed8397fad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584193"
---
# <a name="use-annotations-in-packages"></a><span data-ttu-id="dba22-102">Usar anotações em pacotes</span><span class="sxs-lookup"><span data-stu-id="dba22-102">Use Annotations in Packages</span></span>
  <span data-ttu-id="dba22-103">O [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer fornece anotações, que você pode usar para fazer pacotes de autodocumentação e mais fáceis de entender e manter.</span><span class="sxs-lookup"><span data-stu-id="dba22-103">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides annotations, which you can use to make packages self-documenting and easier to understand and maintain.</span></span> <span data-ttu-id="dba22-104">Você pode adicionar anotações ao fluxo de controle, fluxo de dados e superfícies de design do manipulador de eventos do [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span><span class="sxs-lookup"><span data-stu-id="dba22-104">You can add annotations to the control flow, data flow, and event handler design surfaces of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="dba22-105">As anotações podem conter qualquer tipo de texto e são úteis para adicionar rótulos, comentários e outras informações descritivas para um pacote.</span><span class="sxs-lookup"><span data-stu-id="dba22-105">The annotations can contain any type of text, and they are useful for adding labels, comments, and other descriptive information to a package.</span></span> <span data-ttu-id="dba22-106">As anotações são um recurso de tempo de design apenas.</span><span class="sxs-lookup"><span data-stu-id="dba22-106">Annotations are a design-time feature only.</span></span> <span data-ttu-id="dba22-107">Por exemplo, elas não são gravadas nos logs.</span><span class="sxs-lookup"><span data-stu-id="dba22-107">For example, they are not written to logs.</span></span>  
  
 <span data-ttu-id="dba22-108">Quando você pressiona ENTER, o texto é quebrado para a próxima linha.</span><span class="sxs-lookup"><span data-stu-id="dba22-108">When you press ENTER, the text wraps to the next line.</span></span> <span data-ttu-id="dba22-109">A caixa de anotação automaticamente aumenta de tamanho à medida que você adiciona linhas de texto.</span><span class="sxs-lookup"><span data-stu-id="dba22-109">The annotation box automatically increases in size as you add additional lines of text.</span></span> <span data-ttu-id="dba22-110">As anotações de pacote são persistidas como texto não criptografado na seção CDATA do arquivo de pacote.</span><span class="sxs-lookup"><span data-stu-id="dba22-110">Package annotations are persisted as clear text in the CDATA section of the package file.</span></span>  
  
 <span data-ttu-id="dba22-111">Para obter mais informações sobre as alterações ao formato do arquivo de pacote, consulte [Formato do pacote SSIS](../../2014/integration-services/ssis-package-format.md).</span><span class="sxs-lookup"><span data-stu-id="dba22-111">For more information about changes to the format of the package file, see [SSIS Package Format](../../2014/integration-services/ssis-package-format.md).</span></span>  
  
 <span data-ttu-id="dba22-112">Quando você salva o pacote, o [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer salva as anotações no pacote.</span><span class="sxs-lookup"><span data-stu-id="dba22-112">When you save the package, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the annotations in the package.</span></span>  
  
### <a name="to-add-an-annotation-to-a-package"></a><span data-ttu-id="dba22-113">Para adicionar uma anotação a um pacote</span><span class="sxs-lookup"><span data-stu-id="dba22-113">To add an annotation to a package</span></span>  
  
-   [<span data-ttu-id="dba22-114">Adicionar uma anotação a um pacote</span><span class="sxs-lookup"><span data-stu-id="dba22-114">Add an Annotation to a Package</span></span>](../../2014/integration-services/add-an-annotation-to-a-package.md)  
  
  
