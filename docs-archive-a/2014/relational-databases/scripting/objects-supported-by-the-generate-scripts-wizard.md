---
title: Objetos com suporte no Assistente para Gerar Scripts
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 071eb2cb-f073-41ca-9f4d-11d3b8803495
author: rothja
ms.author: jroth
ms.openlocfilehash: 5ddc1da0d2f87fc12dfbe034a683802f54b7d34f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582408"
---
# <a name="objects-supported-by-the-generate-scripts-wizard"></a><span data-ttu-id="5156a-102">Objetos com suporte no Assistente para Gerar Scripts</span><span class="sxs-lookup"><span data-stu-id="5156a-102">Objects Supported by the Generate Scripts Wizard</span></span>
  <span data-ttu-id="5156a-103">O Assistente para Gerar e Publicar Scripts oferece suporte a um subconjunto dos objetos com suporte no [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5156a-103">The Generate and Publish Scripts wizard supports a subset of the objects supported by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="supported-objects"></a><span data-ttu-id="5156a-104">Objetos com suporte</span><span class="sxs-lookup"><span data-stu-id="5156a-104">Supported Objects</span></span>  
 <span data-ttu-id="5156a-105">A seguinte tabela lista os objetos que podem ser publicados e as versões com suporte do Assistente para Gerar e Publicar Scripts.</span><span class="sxs-lookup"><span data-stu-id="5156a-105">The following table lists the objects that can be published supported by the Generate and Publish Scripts Wizard.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="5156a-106">Função de aplicativo</span><span class="sxs-lookup"><span data-stu-id="5156a-106">Application role</span></span>|<span data-ttu-id="5156a-107">Função de banco de dados</span><span class="sxs-lookup"><span data-stu-id="5156a-107">Database role</span></span>|<span data-ttu-id="5156a-108">Esquema</span><span class="sxs-lookup"><span data-stu-id="5156a-108">Schema</span></span>|<span data-ttu-id="5156a-109">Agregação definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="5156a-109">User-defined aggregate</span></span>|<span data-ttu-id="5156a-110">Exibição<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5156a-110">View<sup>1</sup></span></span>|  
|<span data-ttu-id="5156a-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="5156a-111">Assembly</span></span>|<span data-ttu-id="5156a-112">Restrição DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5156a-112">DEFAULT constraint</span></span>|<span data-ttu-id="5156a-113">Procedimento armazenado<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5156a-113">Stored procedure<sup>1</sup></span></span>|<span data-ttu-id="5156a-114">Tipo de dados definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="5156a-114">User-defined data type</span></span>|<span data-ttu-id="5156a-115">Coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="5156a-115">XML schema collection</span></span>|  
|<span data-ttu-id="5156a-116">Restrição CHECK</span><span class="sxs-lookup"><span data-stu-id="5156a-116">CHECK constraint</span></span>|<span data-ttu-id="5156a-117">Catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="5156a-117">Full-text catalog</span></span>|<span data-ttu-id="5156a-118">Sinônimo</span><span class="sxs-lookup"><span data-stu-id="5156a-118">Synonym</span></span>|<span data-ttu-id="5156a-119">Função definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="5156a-119">User-defined function</span></span>||  
|<span data-ttu-id="5156a-120">Procedimento armazenado do CLR (Common Language Runtime)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5156a-120">CLR (common language runtime) stored procedure<sup>1</sup></span></span>|<span data-ttu-id="5156a-121">Índice</span><span class="sxs-lookup"><span data-stu-id="5156a-121">Index</span></span>|<span data-ttu-id="5156a-122">Tabela</span><span class="sxs-lookup"><span data-stu-id="5156a-122">Table</span></span>|<span data-ttu-id="5156a-123">Tabela definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="5156a-123">User-defined table</span></span>||  
|<span data-ttu-id="5156a-124">Função CLR definida pelo usuário</span><span class="sxs-lookup"><span data-stu-id="5156a-124">CLR user-defined function</span></span>|<span data-ttu-id="5156a-125">Regra</span><span class="sxs-lookup"><span data-stu-id="5156a-125">Rule</span></span>|<span data-ttu-id="5156a-126">Usuário<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5156a-126">User<sup>2</sup></span></span>|<span data-ttu-id="5156a-127">Tipo definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="5156a-127">User-defined type</span></span>||  
  
 <span data-ttu-id="5156a-128"><sup>1</sup> publicado sem criptografia.</span><span class="sxs-lookup"><span data-stu-id="5156a-128"><sup>1</sup> Published without encryption.</span></span>  
  
 <span data-ttu-id="5156a-129"><sup>2</sup> os usuários que não são do sistema existentes no banco de dados são publicados como funções.</span><span class="sxs-lookup"><span data-stu-id="5156a-129"><sup>2</sup> Any non-system users that exist in the database are published as Roles.</span></span>  
  
  
