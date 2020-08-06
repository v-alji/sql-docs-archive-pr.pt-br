---
title: Objeto SqlXmlAdapter (classes gerenciadas SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- void Update(DataSet ds) method
- SqlXmlAdapter object
- void Fill(DataSet ds) method
- SQLXML Managed Classes, SqlXmlAdapter object
- Managed Classes [SQLXML], SqlXmlAdapter object
ms.assetid: 0a16eddf-fc26-4d92-82d4-359b5fb905d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 1357ab7d070c7c2e451e31bccfda22c58eac42d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569302"
---
# <a name="sqlxmladapter-object-sqlxml-managed-classes"></a><span data-ttu-id="1daa9-102">Objeto SqlXmlAdapter (classes gerenciadas SQLXML)</span><span class="sxs-lookup"><span data-stu-id="1daa9-102">SqlXmlAdapter Object (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="1daa9-103">Este objeto fornece métodos que facilitam a interação com o conjunto de dados no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1daa9-103">This object provides methods that facilitate interaction with the dataset in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="1daa9-104">Para obter um exemplo funcional, consulte [acessando a funcionalidade SQLXML no ambiente .net](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1daa9-104">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="1daa9-105">O objeto SqlXmlAdapter dá suporte a esses métodos:</span><span class="sxs-lookup"><span data-stu-id="1daa9-105">The SqlXmlAdapter object supports these methods:</span></span>  
  
 <span data-ttu-id="1daa9-106">void Fill (DataSet DS)</span><span class="sxs-lookup"><span data-stu-id="1daa9-106">void Fill(DataSet ds)</span></span>  
 <span data-ttu-id="1daa9-107">Preenche o conjunto de dados no .NET Framework com os dados XML recuperados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1daa9-107">Fills the dataset in the .NET Framework with the XML data retrieved from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1daa9-108">anular atualização (DataSet DS)</span><span class="sxs-lookup"><span data-stu-id="1daa9-108">void Update(DataSet ds)</span></span>  
 <span data-ttu-id="1daa9-109">Aplica atualizações a registros no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a partir dos dados do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="1daa9-109">Applies updates to records in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the data in the dataset.</span></span>  
  
 <span data-ttu-id="1daa9-110">O objeto SqlXmlAdapter dá suporte a esses construtores:</span><span class="sxs-lookup"><span data-stu-id="1daa9-110">The SqlXmlAdapter object supports these constructors:</span></span>  
  
```  
public SqlXmlAdapter(SqlXmlCommand  cmd)   
  
public SqlXmlAdapter(  
                     string commandText,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                      )   
  
public SqlXmlAdapter(  
                     Stream commandStream,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                     )   
```  
  
## <a name="see-also"></a><span data-ttu-id="1daa9-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1daa9-111">See Also</span></span>  
 <span data-ttu-id="1daa9-112">[Objeto SqlXmlCommand &#40;classes gerenciadas SQLXML&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="1daa9-112">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 [<span data-ttu-id="1daa9-113">Objeto SqlXmlParameter &#40;classes gerenciadas SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="1daa9-113">SqlXmlParameter Object &#40;SQLXML Managed Classes&#41;</span></span>](sqlxml-managed-classes-sqlxmlparameter-object.md)  
  
  
