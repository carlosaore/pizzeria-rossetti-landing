<script setup></script>
<template>
  <div class="field">
    <label class="label">Tu Nombre</label>
    <div class="control">
      <input class="input" placeholder="Text input" type="text" />
    </div>
  </div>
  <div class="field">
    <label class="label">Tu Email</label>
    <div class="control has-icons-left has-icons-right">
      <input class="input" type="email" />
      <span class="icon is-small is-left">
        <i>@</i>
      </span>
    </div>
  </div>
  <div class="field">
    <label class="label">Mensaje</label>
    <div class="control">
      <textarea class="textarea" placeholder="Textarea"></textarea>
    </div>
  </div>
  <div class="control">
    <button class="button is-link">Enviar</button>
  </div>
</template>
