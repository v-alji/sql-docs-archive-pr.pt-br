---
title: Metadados de parâmetro com valor de tabela para instruções preparadas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), metadata for prepared statements
ms.assetid: fd2fc705-2e98-4011-9822-c7e6cca4a535
author: rothja
ms.author: jroth
ms.openlocfilehash: ad1394bd5e5bedc69a98308ba67a98434559c146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685618"
---
# <a name="table-valued-parameter-metadata-for-prepared-statements"></a><span data-ttu-id="e0e96-102">Metadados do parâmetro com valor de tabela para instruções preparadas</span><span class="sxs-lookup"><span data-stu-id="e0e96-102">Table-Valued Parameter Metadata for Prepared Statements</span></span>
  <span data-ttu-id="e0e96-103">Um aplicativo pode obter metadados para uma chamada de procedimento preparada por meio de SQLNumParams e SQLDescribeParam.</span><span class="sxs-lookup"><span data-stu-id="e0e96-103">An application can obtain metadata for a prepared procedure call through SQLNumParams and SQLDescribeParam.</span></span> <span data-ttu-id="e0e96-104">Para parâmetros com valor de tabela, *DataTypePtr* é definido como SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="e0e96-104">For table-valued parameters, *DataTypePtr* is set to SQL_SS_TABLE.</span></span> <span data-ttu-id="e0e96-105">Os metadados adicionais estão disponíveis por meio do SQLGetDescField para SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME e SQL_CA_SS_SCHEMA_NAME.</span><span class="sxs-lookup"><span data-stu-id="e0e96-105">Additional metadata is available through SQLGetDescField for SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME.</span></span>  
  
 <span data-ttu-id="e0e96-106">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME e SQL_CA_SS_SCHEMA_NAME podem ser usados com SQLColumns para obter metadados de coluna para tipos de tabela associados a parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="e0e96-106">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME can be used with SQLColumns to obtain column metadata for table types associated with table-valued parameters.</span></span> <span data-ttu-id="e0e96-107">Nesse caso, SQL_SOPT_SS_NAME_SCOPE deve ser definido como SQL_SS_NAME_SCOPE_TABLE_TYPE antes que SQLColumns seja chamado.</span><span class="sxs-lookup"><span data-stu-id="e0e96-107">In this case, SQL_SOPT_SS_NAME_SCOPE must be set to SQL_SS_NAME_SCOPE_TABLE_TYPE before SQLColumns is called.</span></span> <span data-ttu-id="e0e96-108">SQL_SOPT_SS_NAME_SCOPE deve ser definido novamente com o valor padrão, SQL_SS_NAME_SCOPE_TABLE, quando o aplicativo concluir a recuperação de metadados da coluna do parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="e0e96-108">SQL_SOPT_SS_NAME_SCOPE should then be set back to the default value, SQL_SS_NAME_SCOPE_TABLE, when the application has finished retrieving table-valued parameter column metadata.</span></span>  
  
 <span data-ttu-id="e0e96-109">SQL_CA_SS_TYPE_NAME , SQL_CA_SS_CATALOG_NAME e SQL_CA_SS_SCHEMA_NAME também podem ser usados com parâmetros de tipo de dado CLR definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="e0e96-109">SQL_CA_SS_TYPE_NAME , SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME can also be used with CLR user-defined type parameters.</span></span>  
  
 <span data-ttu-id="e0e96-110">Você não pode obter metadados de parâmetro com valor de tabela para instruções preparadas que não são chamadas de procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="e0e96-110">You cannot obtain table-valued parameter metadata for prepared statements that are not stored procedure calls.</span></span> <span data-ttu-id="e0e96-111">Se você tentar fazer isto, o aplicativo retornará SQL_ERROR com SQLSTATE 42000 e a mensagem "Erro de sintaxe ou violação de acesso".</span><span class="sxs-lookup"><span data-stu-id="e0e96-111">If you try to do this, the application returns SQL_ERROR with SQLSTATE 42000 and the message "Syntax error or access violation".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e96-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e0e96-112">See Also</span></span>  
 [<span data-ttu-id="e0e96-113">Parâmetros com valor de tabela &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="e0e96-113">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
