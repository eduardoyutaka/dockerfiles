FROM elixir:latest

WORKDIR /my-app

COPY ./mix* ./

RUN mix local.hex --force \
    mix deps.get \
    mix local.rebar --force

COPY ./ ./

RUN mix compile

ENTRYPOINT ["bash", "/my-app/entrypoint.sh"]
