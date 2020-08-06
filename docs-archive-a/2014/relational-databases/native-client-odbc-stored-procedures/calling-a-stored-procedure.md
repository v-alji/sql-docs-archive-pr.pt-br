---
title: Chamando um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- ODBC, stored procedures
- stored procedures [ODBC], calling
- SQL Server Native Client ODBC driver, stored procedures
- ODBC CALL escape sequence
- escape sequences [SQL Server]
- CALL statement
ms.assetid: d13737f4-f641-45bf-b56c-523e2ffc080f
author: rothja
ms.author: jroth
ms.openlocfilehash: c6fa704e45e4e85b479ae8a40a3e567bea1ec5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685625"
---
# <a name="calling-a-stored-procedure"></a><span data-ttu-id="5a55b-102">Chamando um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="5a55b-102">Calling a Stored Procedure</span></span>
  <span data-ttu-id="5a55b-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client dá suporte à sequência de escape de chamada ODBC e à [!INCLUDE[tsql](../../includes/tsql-md.md)] instrução [Execute](/sql/t-sql/language-elements/execute-transact-sql) para executar procedimentos armazenados; a sequência de escape de chamada ODBC é o método preferencial.</span><span class="sxs-lookup"><span data-stu-id="5a55b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports both the ODBC CALL escape sequence and the [!INCLUDE[tsql](../../includes/tsql-md.md)][EXECUTE](/sql/t-sql/language-elements/execute-transact-sql) statement for executing stored procedures; the ODBC CALL escape sequence is the preferred method.</span></span> <span data-ttu-id="5a55b-104">Usar a sintaxe ODBC permite que um aplicativo recupere os códigos de retorno dos procedimentos armazenados e o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client também é otimizado para usar um protocolo originalmente desenvolvido para enviar RPCs (chamadas de procedimento remoto) entre computadores que estejam executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a55b-104">Using ODBC syntax enables an application to retrieve the return codes of stored procedures and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is also optimized to use a protocol originally developed for sending remote procedure (RPC) calls between computers running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5a55b-105">Este protocolo de RPC aumenta o desempenho, eliminando grande parte do processamento de parâmetros e da análise da instrução feita no servidor.</span><span class="sxs-lookup"><span data-stu-id="5a55b-105">This RPC protocol increases performance by eliminating much of the parameter processing and statement parsing done on the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a55b-106">Ao chamar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procedimentos armazenados usando parâmetros nomeados com ODBC (para obter mais informações, consulte [parâmetros de associação por nome (parâmetros nomeados)](https://go.microsoft.com/fwlink/?LinkID=209721)), os nomes de parâmetro devem começar com o \@ caractere ' '.</span><span class="sxs-lookup"><span data-stu-id="5a55b-106">When calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures using named parameters with ODBC (for more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkID=209721)), the parameter names must start with the '\@' character.</span></span> <span data-ttu-id="5a55b-107">Esta é uma restrição específica do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a55b-107">This is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specific restriction.</span></span> <span data-ttu-id="5a55b-108">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client impõe esta restrição de forma mais rigorosa que os MDAC (Microsoft Data Access Components).</span><span class="sxs-lookup"><span data-stu-id="5a55b-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enforces this restriction more strictly than the Microsoft Data Access Components (MDAC).</span></span>  
  
 <span data-ttu-id="5a55b-109">A sequência de escape CALL do ODBC para chamar um procedimento é:</span><span class="sxs-lookup"><span data-stu-id="5a55b-109">The ODBC CALL escape sequence for calling a procedure is:</span></span>  
  
 <span data-ttu-id="5a55b-110">{[**? =**]**chamar**_procedure_name_[([*parâmetro*] [**,**[*Parameter*]]...)]}</span><span class="sxs-lookup"><span data-stu-id="5a55b-110">{[**?=**]**call**_procedure_name_[([*parameter*][**,**[*parameter*]]...)]}</span></span>  
  
 <span data-ttu-id="5a55b-111">em que *procedure_name* especifica o nome de um procedimento e o *parâmetro* especifica um parâmetro de procedimento.</span><span class="sxs-lookup"><span data-stu-id="5a55b-111">where *procedure_name* specifies the name of a procedure and *parameter* specifies a procedure parameter.</span></span> <span data-ttu-id="5a55b-112">Há suporte para parâmetros nomeados somente em instruções que usam a sequência de escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="5a55b-112">Named parameters are only supported in statements using the ODBC CALL escape sequence.</span></span>  
  
 <span data-ttu-id="5a55b-113">Um procedimento pode ter zero ou mais parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5a55b-113">A procedure can have zero or more parameters.</span></span> <span data-ttu-id="5a55b-114">Ele também pode retornar um valor (conforme indicado pelo marcador de parâmetro opcional ?= no início da sintaxe).</span><span class="sxs-lookup"><span data-stu-id="5a55b-114">It can also return a value (as indicated by the optional parameter marker ?= at the start of the syntax).</span></span> <span data-ttu-id="5a55b-115">Se um parâmetro for de entrada ou entrada/saída, poderá ser um literal ou um marcador de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5a55b-115">If a parameter is an input or an input/output parameter, it can be a literal or a parameter marker.</span></span> <span data-ttu-id="5a55b-116">Se o parâmetro for de saída, deve ser um marcador de parâmetro, porque a saída é desconhecida.</span><span class="sxs-lookup"><span data-stu-id="5a55b-116">If the parameter is an output parameter, it must be a parameter marker because the output is unknown.</span></span> <span data-ttu-id="5a55b-117">Os marcadores de parâmetro devem ser associados a [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) antes que a instrução de chamada de procedimento seja executada.</span><span class="sxs-lookup"><span data-stu-id="5a55b-117">Parameter markers must be bound with [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) before the procedure call statement is executed.</span></span>  
  
 <span data-ttu-id="5a55b-118">Parâmetros de entrada e entrada/saída podem ser omitidos das chamadas de procedimento.</span><span class="sxs-lookup"><span data-stu-id="5a55b-118">Input and input/output parameters can be omitted from procedure calls.</span></span> <span data-ttu-id="5a55b-119">Se um procedimento for chamado usando parênteses, mas sem nenhum parâmetro, o driver instruirá a fonte de dados a usar o valor padrão para o primeiro parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5a55b-119">If a procedure is called with parentheses but without any parameters, the driver instructs the data source to use the default value for the first parameter.</span></span> <span data-ttu-id="5a55b-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5a55b-120">For example:</span></span>  
  
 <span data-ttu-id="5a55b-121">{**chamar** _procedure_name_**()**}</span><span class="sxs-lookup"><span data-stu-id="5a55b-121">{**call** _procedure_name_**( )**}</span></span>  
  
 <span data-ttu-id="5a55b-122">Se o procedimento não tiver nenhum parâmetro, ele poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="5a55b-122">If the procedure does not have any parameters, the procedure can fail.</span></span> <span data-ttu-id="5a55b-123">Se um procedimento for chamado sem parênteses, o driver não enviará nenhum valor de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5a55b-123">If a procedure is called without parentheses, the driver does not send any parameter values.</span></span> <span data-ttu-id="5a55b-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5a55b-124">For example:</span></span>  
  
 <span data-ttu-id="5a55b-125">{**chamar** _procedure_name_}</span><span class="sxs-lookup"><span data-stu-id="5a55b-125">{**call** _procedure_name_}</span></span>  
  
 <span data-ttu-id="5a55b-126">Literais podem ser especificados para parâmetros de entrada e de entrada/saída em chamadas de procedimento.</span><span class="sxs-lookup"><span data-stu-id="5a55b-126">Literals can be specified for input and input/output parameters in procedure calls.</span></span> <span data-ttu-id="5a55b-127">Por exemplo, o procedimento InsertOrder tem cinco parâmetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="5a55b-127">For example, the procedure InsertOrder has five input parameters.</span></span> <span data-ttu-id="5a55b-128">A seguinte chamada a InsertOrder omite o primeiro parâmetro, fornece um literal para o segundo parâmetro e usa um marcador de parâmetro para o terceiro, quarto e quinto parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5a55b-128">The following call to InsertOrder omits the first parameter, provides a literal for the second parameter, and uses a parameter marker for the third, fourth, and fifth parameters.</span></span> <span data-ttu-id="5a55b-129">(Os parâmetros são numerados sequencialmente, a partir do valor 1.)</span><span class="sxs-lookup"><span data-stu-id="5a55b-129">(Parameters are numbered sequentially, beginning with a value of 1.)</span></span>  
  
```  
{call InsertOrder(, 10, ?, ?, ?)}  
```  
  
 <span data-ttu-id="5a55b-130">Observe que, se um parâmetro for omitido, a vírgula que o separa de outros parâmetros ainda precisará aparecer.</span><span class="sxs-lookup"><span data-stu-id="5a55b-130">Note that if a parameter is omitted, the comma delimiting it from other parameters must still appear.</span></span> <span data-ttu-id="5a55b-131">Se um parâmetro de entrada ou entrada/saída for omitido, o procedimento usará o valor padrão do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5a55b-131">If an input or input/output parameter is omitted, the procedure uses the default value of the parameter.</span></span> <span data-ttu-id="5a55b-132">Outras formas de especificar o valor padrão de um parâmetro de entrada ou entrada/saída são definir o valor do buffer de comprimento/indicador associado ao parâmetro como SQL_DEFAULT_PARAM, ou usar a palavra-chave DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="5a55b-132">Other ways to specify the default value of an input or input/output parameter are to set the value of the length/indicator buffer bound to the parameter to SQL_DEFAULT_PARAM, or to use the DEFAULT keyword.</span></span>  
  
 <span data-ttu-id="5a55b-133">Se um parâmetro de entrada/saída for omitido ou se for fornecido um literal para o parâmetro, o driver descartará o valor de saída.</span><span class="sxs-lookup"><span data-stu-id="5a55b-133">If an input/output parameter is omitted, or if a literal is supplied for the parameter, the driver discards the output value.</span></span> <span data-ttu-id="5a55b-134">De forma semelhante, se o marcador de parâmetro para o valor de retorno de um procedimento for omitido, o driver descartará o valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="5a55b-134">Similarly, if the parameter marker for the return value of a procedure is omitted, the driver discards the return value.</span></span> <span data-ttu-id="5a55b-135">Finalmente, se um aplicativo especificar um parâmetro de valor de retorno para um procedimento que não retorna um valor, o driver definirá o valor do buffer de comprimento/indicador associado ao parâmetro como SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="5a55b-135">Finally, if an application specifies a return value parameter for a procedure that does not return a value, the driver sets the value of the length/indicator buffer bound to the parameter to SQL_NULL_DATA.</span></span>  
  
## <a name="delimiters-in-call-statements"></a><span data-ttu-id="5a55b-136">Delimitadores em instruções CALL</span><span class="sxs-lookup"><span data-stu-id="5a55b-136">Delimiters in CALL Statements</span></span>  
 <span data-ttu-id="5a55b-137">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, por padrão, também dá suporte uma opção de compatibilidade específica para a sequência de escape {CALL} do ODBC.</span><span class="sxs-lookup"><span data-stu-id="5a55b-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by default also supports a compatibility option specific to the ODBC { CALL } escape sequence.</span></span> <span data-ttu-id="5a55b-138">O driver aceita instruções CALL com um único conjunto de aspas duplas que delimitam o nome de procedimento armazenado inteiro:</span><span class="sxs-lookup"><span data-stu-id="5a55b-138">The driver accepts CALL statements with only a single set of double quotation marks delimiting the entire stored procedure name:</span></span>  
  
```  
{ CALL "master.dbo.sp_who" }  
```  
  
 <span data-ttu-id="5a55b-139">Por padrão, o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client também aceita instruções CALL que seguem as regras ISO e colocam cada identificador entre aspas duplas:</span><span class="sxs-lookup"><span data-stu-id="5a55b-139">By default the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver also accepts CALL statements that follow the ISO rules and enclose each identifier in double quotation marks:</span></span>  
  
```  
{ CALL "master"."dbo"."sp_who" }  
```  
  
 <span data-ttu-id="5a55b-140">Entretanto, ao ser executado com as configurações padrão, o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client não dá suporte ao uso de nenhuma forma de identificador entre aspas com identificadores que contenham caracteres que não sejam especificados como válidos em identificadores, de acordo com a norma ISO.</span><span class="sxs-lookup"><span data-stu-id="5a55b-140">When running with the default settings, however, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using either form of quoted identifier with identifiers that contain characters not specified as legal in identifiers by the ISO standard.</span></span> <span data-ttu-id="5a55b-141">Por exemplo, o driver não pode acessar um procedimento armazenado chamado **"My. proc"** usando uma instrução Call com identificadores entre aspas:</span><span class="sxs-lookup"><span data-stu-id="5a55b-141">For example, the driver cannot access a stored procedure named **"My.Proc"** using a CALL statement with quoted identifiers:</span></span>  
  
```  
{ CALL "MyDB"."MyOwner"."My.Proc" }  
```  
  
 <span data-ttu-id="5a55b-142">Esta instrução é interpretada pelo driver como:</span><span class="sxs-lookup"><span data-stu-id="5a55b-142">This statement is interpreted by the driver as:</span></span>  
  
```  
{ CALL MyDB.MyOwner.My.Proc }  
```  
  
 <span data-ttu-id="5a55b-143">O servidor gera um erro de que um servidor vinculado denominado **mydb** não existe.</span><span class="sxs-lookup"><span data-stu-id="5a55b-143">The server raises an error that a linked server named **MyDB** does not exist.</span></span>  
  
 <span data-ttu-id="5a55b-144">O problema não existe ao usar identificadores entre colchetes, esta instrução é interpretada corretamente:</span><span class="sxs-lookup"><span data-stu-id="5a55b-144">The issue does not exist when using bracketed identifiers, this statement is interpreted correctly:</span></span>  
  
```  
{ CALL [MyDB].[MyOwner].[My.Table] }  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a55b-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5a55b-145">See Also</span></span>  
 [<span data-ttu-id="5a55b-146">Executando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="5a55b-146">Running Stored Procedures</span></span>](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
  
