---
layout:     post
title:      "Nuevo post"
subtitle:   "Primera entrada."
date:       2015-06-24 18:00:00
author:     "Ernesto Bossi"
header-img: "img/post-bg-01.jpg"
---

## Este es un titulo

Esto es un stub para futuros posts en caso que decidamos armar explicaciones propias.

<blockquote>The dreams of yesterday are the hopes of today and the reality of tomorrow. Science has not yet mastered prophecy. We predict too much for the next year and yet far too little for the next ten.</blockquote>

{% highlight elixir %}
defmodule ListSearch do

  def search_pattern([], element_atom) do
    {:error, :none_found}
  end
  def search_pattern([x|xs], element_atom) do
    case x == element_atom do
      true -> {:ok, x}
      false -> search_pattern(xs, element_atom)
    end
  end
end

defmodule EtsStore do

  def new_table(table_name) do
    :ets.new(table_name, [:public, :named_table])
  end

  def is_table_defined(table_name) do
    ListSearch.search_pattern(:ets.all(),table_name)
  end

  def get(table, key) do
    case :ets.lookup(table, key) do
	[{_key, value}] -> {:ok, value}
	[] -> {:error, :not_found}
    end
  end

  def put(table, key, value) do
    :ets.insert(table, {key, value})
  end

  def delete(table, key) do
    :ets.match_delete(table, {key, :_})
  end

  def update(table, key, new_value) do
     case :ets.lookup(table, key) do
     	[{_key, value}] -> delete(table, key)
			   put(table, key, new_value)
	[] -> {:error, :not_found}
     end
  end

end
{% endhighlight %}